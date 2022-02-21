---
layout: post
title: "Procedure"
date: 2020-01-01
background: '/img/posts/03.jpg'
categories: posts/mssql
sitemap:
changefreq: daily
priority: 1.0
---
<p></p>

<!-- <h5 class="section-heading"> Procedure </h5> -->
## Procedure 생성
```sql
CREATE PROCEDURE [database명].[프로시저명]
AS
[쿼리문]
```

```sql
CREATE PROCEDURE [dbo].[GET_Branch]
    -- 매개변수와 컬럼의 데이터 타입을 일치시켜 줄 것 
	@ELevel       int,
	@CompanyCode  nvarchar(20) = 'hskim'
AS
BEGIN
    SET TRANSACTION ISOLATION LEVEL READ UNCOMMITTED;
    SET NOCOUNT ON; -- *

	WITH BRANCHLEVEL (BranchID, BranchName, ParentCode, SortOrder, PhoneNumber, [LEVEL])
	AS
	(
		SELECT A.BranchID
		       ,A.BranchName
			,A.ParentCode
			,A.SortOrder
			,A.PhoneNumber
			,0 AS [LEVEL]
		FROM T_Branch  A
		WHERE ParentCode IS NULL
		AND CompanyCode = @CompanyCode

		UNION ALL

		SELECT B.BranchID
		       ,B.BranchName
			,B.ParentCode
			,B.SortOrder
			,B.PhoneNumber
			,[LEVEL] + 1
		FROM T_Branch B JOIN BRANCHLEVEL AS DL ON
			B.ParentCode = DL.BranchID
		WHERE DL.LEVEL < @ELevel
		AND CompanyCode = @CompanyCode
	)

	SELECT BranchID, 
			BranchName, 
			ParentCode, 
			SortOrder, 
			CASE [LEVEL] WHEN 0 THEN ''
				         WHEN 1 THEN ''
						 ELSE
						PhoneNumber END PhoneNumber, 
			[LEVEL]
	FROM BRANCHLEVEL
	ORDER BY [LEVEL], 
		LEN(SortOrder),
		SortOrder, BranchID  

END
GO
```

- > SET NOCOUNT란?<br>
        >  &nbsp;프로시저 실행 후 (0개의 행이 영향을 받음)과 같은 메세지가 출력이 되는데<br> 
        >  &nbsp; SET NOCOUNT ON이라는 문구를 삽입해줌으로써 제거 가능<br>

- > @@ ERROR 시스템 함수?<br>
        >  &nbsp; 마지막 Transact-SQL문이 실행되면 0 반환, 오류 발생 시 오류번호 반환<br> 
        >  &nbsp; @@ERROR값은 Transact-SQL문이 완료될 때 마다 값이 변경<br>
        >  &nbsp; 오류에 대해서만 발생하고 경고에 대해서는 발생하지 않음


## Procedure 삭제
```sql
DROP PROCEDURE dbo.USP_SelectCompanyList
```

## Procedure 호출
```sql
EXEC dbo.USP_SelectCompanyList '99', '세글', '테스트팀', '외부'
```