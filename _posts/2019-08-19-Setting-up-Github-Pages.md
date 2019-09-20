---
layout: post
title: "Setting up Github Pages with Jekyll"
subtitle: "Host a website on Github using Jekyll Theme with Ruby on Windows"
date: 2019-08-19
background: '/img/posts/05.jpg'
categories : posts/jekyll
sitemap :
changefreq : daily
priority : 1.0
---
<h1>Setting up Github Pages with Jekyll</h1>
<p>This is a quick summary to build Github Pages with Jekyll Theme on Windows</p>

<h2 class="section-heading">1. RubyInstaller</h2>
<h5>1-1. If you don´t have Ruby installed, install Ruby with Development Kit</h5>
<a href="https://rubyinstaller.org/downloads/">https://rubyinstaller.org/downloads</a>
<img class="img-fluid" src="/img/posts/190819/rubyinstaller.PNG" alt="RubyInstaller Page">

<h5>1-2. Install MSYS2 following instructions for Ruby Installer</h5>
<h5>1-3. Check the version of Ruby after installation on Ruby Command Prompt</h5>
<pre class="highlight"><code>C:\>ruby -v</code></pre>

<h2 class="section-heading">2. Install Jekyll</h2>
<p>You can install Jekyll using gem since Ruby is installed</p>
<p>On Ruby Command Prompt,</p>
<pre class="highlight"><code>$ gem install jekyll bundler
$ jekyll -v</code></pre>

<h2 class="section-heading">3. Adding a Jekyll theme to your GitHub Pages</h2>
<p>There are many ways to add a Jekyll theme to your repository. In my case, I downloaded Jekyll theme(Clean-Blog) and copied it to my repository.</p>

<h5>3-1. Create Jekyll on local directory</h5>
<pre class="highlight"><code>$ jekyll new [GithubUsername].github.io</code></pre>

<p>Enter the directory you have just made.</p>
<pre class="highlight"><code>$ cd [GithubUsername]</code></pre>

<p>There are few more steps left, but publish the blog locally to see if it works well.</p>
<pre class="highlight"><code>$ bundle exec jekyll serve</code></pre>

<p>The site should be up and running on local host:</p>
<http://127.0.0.1:4000/>

<h5>3-2. Download or Clone a Jekyll Theme.</h5>
<h5>3-3. Copied files to your repository.</h5>
<h5>3-4. Edit _config.yml. For example, </h5>
<pre class="highlight">
baseurl:            
url:   "https://hskim2019.github.io"</pre>

<h2 class="section-heading">4. Host a website on Github</h2>
<h5>4-1. Create a repository named [GithubUsername].github.io</h5>
<h5>4-2. Push your changes to your remote repository on GitHub.</h5>


