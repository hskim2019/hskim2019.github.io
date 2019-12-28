---
layout: post
title: "Summary note"
date: 2019-09-20
background: '/img/posts/02.jpg'
categories: posts/spring
sitemap:
changefreq: daily
priority: 1.0
---
<p></p>

<h5 class="section-heading"> Framework 구성요소</h5>
<p>Ioc, Class Library, Design pattern</p><br>

- 디자인 패턴은 가이드라인, 
    프레임워크는 디자인패턴을 이용하여 만든 재사용 가능한 라이브러리로서 
    어플리케이션의 최소한의 공통점을 찾아 비기능적 요구사항을 만족하는 구조를 제공하기 때문에 
    개발자들은 이를 활용하여 기능적 요구사항에 더 집중할 수 있음

- Inversion of Control - 제어의 역전

- 개발자가 라이브러리를 사용하면
유저 코드가 라이브러리 코드를 호출하여 개발자가 제어함
개발자가 프레임워크 사용 시 프레임워크 코드가 유저코드를 호출하며 인스턴스 생성주기를 관리 함
제어가 역전 됨
  

<h5 class="section-heading"> Framework 종류</h5>  


| Function                           | Framework                  |
|------------------------------------|----------------------------|
| web(mvc)                           | Spring MVC                 |
| Object-Relational mapping          | MyBatis, Spring JDBC       |
| AOP(Aspect Oriented Programming)   | Spring AOP, AspectJ        |
| DI(Dependency Injection)           | Spring DI                  |
| Build & Library management         | Maven, Gradle              |
| Unit test                          | jUnit                      |
| JavaScript                         | jQuery, AngularJS, Node.js |


<h5 class="section-heading"> Spring framework 특징</h5>
컨테이너 역할
- java 객체의 lifecycle 관리
- spring container 로부터 필요한 객체 가져와 사용 가능

DI 지원
- 설정 파일이나 annotation을 통해 객체 간 의존관계 설정 가능

AOP 지원
트랜잭션, 로깅, 보안과 같은 모듈을 핵심 모듈에서 분리해서 적용

POJO 지원
- Spring container에 저장되는 java 객체는 특정 인터페이스를 구현하거나, 특정 클래스를 상속받지 않아도 됨

다양한 API 지원
- MyBatis 등 데이터베이스 처리를 위한 ORM 프레임워크들과 연동 지원

<h5 class="section-heading"> Maven</h5>
- 라이브러리 관리 + 빌드 툴
- 빌드 : compile, jar 파일 생성하고, 배포
- maven과 같은 라이브러리 관리 툴이 없으면 직접 받아서 압축 해제 후 해당 프로젝트에 복사하고(배치) 해야 하지만
maven 과 같은 빌드 툴 사용 시 pom.xlm 설정파일 안에 어떤 라이브러리를 다운 받을 지 설정만 해주면(Dependency) 빌드 및 관리 가능

<h5 class="section-heading">IoC 분류</h5>
- DL(Dependency Lookup) 의존성 검색 : 저장소에 저장되어 있는 Bean에 접근 시 컨테이너가 제공하는 API 사용
- DI (Dependency Injection) 의존성 주입: 각 Class 간의 의존관계를 Bean 설정 정보를 바탕으로 컨테이너가 자동으로 연결해주는 것

<h5 class="section-heading">DI의 개념</h5>
- 설정방법 : XML, annotation
- 코드가 단순해지고, 컨테이너가 주체가 되어 의존관계를 주입해주고 실행 시 동적으로 의존관계 생성 됨
- *bean : Spring이 관리하는 java 객체, container에게 관리를 부탁하는 java 객체들

<h5 class="section-heading">Spring DI 컨테이너의 개념</h5>

* BeanFactory
    - Bean을 관리하는 컨테이너
    - Bean을 등록, 생성, 조회, 반환 관리
    - BeanFactory를 확장한 ApplicationContext 사용

* ApplicationContext
    - BeanFactory에 여러가지 container 기능을 추가한 것


<h5 class="section-heading">Package 관리자</h5>  
라이브러리 설치, 갱신, 삭제를 처리하는 Package Manager/ Dependency Manager


| Language                         | Package Manager                 |
|----------------------------------|---------------------------------|
| JAVA                             | maven, gradle                   |
| Ruby                             | RubyGems, Bundler               |
| .NET                             | nuget                           |
| Python                           | PyPI                            |
| PHP                              | Maven, Gradle                   |
| Node.JS                          | Composer                        |
| JavaScript                       | npm, yarn                       |



