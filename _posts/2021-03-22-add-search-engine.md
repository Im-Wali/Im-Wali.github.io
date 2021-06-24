---
title:  "검색 엔진에 노출하기"
search: false
categories:
  - GithubPage
tags:
  - Gihub Page
  - Jekyll
  - 지킬
  - Google Search Console
---
<br/>
# 검색 엔진에 노출하기
  * 블로그를 한다는 것은 내가 작성한 컨텐츠를 공유를 하겠다는 의미이다. 그럴려면 각종 포털 사이트에서 내가 작성한 포스팅이 검색이 되어야 한다. 이번 포스팅에서는 각종 포털 사이트의 검색 엔진에서 자신의 포스팅을 노출하는 방법에 대해 알아 보겠다.

# 1. Google Search Console

  * Google Search Console은 구글의 전 구글 웹마스터들이 개발한 웹 서비스로서, 웹 마스터들이 자신들의 웹사이트의 보이는 부분을 최적화하고 인덱싱 상태를 검색할 수 있게 한다. [위키백과]

  * Google Search Console은 구글에서 제공하는 웹사이트 무료 툴로 구글에 등록한 자사의 웹사이트를 어떻게 인식하고 있는지 대한 정보를 제공한다. 예전에는 구글 웹 마스터 도구라는 명칭으로 사용하였지만, 현재는 Google Search Cnosole이라는 명칭으로 불리고 있다. 여기에 색인을 추가해야 우리가 힘들게 만든 블로그가 Google 검색 시 나타날 수 있다.


  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-cnosole.png){: .align-center}

# 1-1. Google Search Console 적용하기
 * 우선 Google Search Cnosole를 적용하기 위해서는 로그인이 필요하다. 아래 링크로 이동하여 회원가입 및 로그인을 진행한다.

 * 사이트 주소 : <a href="https://search.google.com/search-console/about" target="_blank">https://search.google.com/search-console/about</a>

 <br/>
![image-center](/assets/images/2021-03-22-google-search-console-starting.png){: .align-center}

 * 설정 추가하여 아래 사진과 같이 "URL 접두어"에 자신의 블로그 URL을 넣는다.
 <br/>
 ![image-center](/assets/images/2021-03-22-google-search-console-insert-url.png){: .align-center}


  * 소유권 확인을 위해서 파일을 다운로드 받는다.
  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-auth-file-down.png){: .align-center}

  * 다운로드 받은 파일을 루트에 위치 시킨다.
  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-save-file.png){: .align-center}


  * 파일를 적용 시키고 소요권 확인 하면 아래와 같은 화면을 볼 수 있다.
  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-complete-auth.png){: .align-center}

# 1-2. Google Search Console sitemap.xml, robots.txt 파일 작성.

  * 이제 내 블로그에 대한 기본 설정이 끝났다. 이제 할 작업은 내가 블로그에 올린 포스팅을 검색 될 수 있게 Sitemap 작업 즉 색인을 생성해야 된다. 현재 내가 사용하고 있는 Jekyll 테마의 경우 기본적으로 _config.yml에 plugin으로 jekyll-sitemap과 jekyll-feed가 추가되어 있기 때문에 Sitemap 파일은 따로 필요 없다. 만약에 자신이 Plugin으로 추가되어 있는지 확인 하고 싶다면 아래와 같이 _config.yml에 설정되어 있는지 확인하고 **https://Im-wali.github.io/sitemap.xml** 링크와 같이 자신 루트 URL에서 뒤에 **sitemap.xml** 붙여 확인해 보면 된다.  

  ```ruby
  # Plugins (previously gems:)
  plugins:
    - jekyll-paginate
    - jekyll-sitemap
    - jekyll-gist
    - jekyll-feed
    - jekyll-include-cache
  ```
  <br/>

  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-sitemap.png){: .align-center}

  * sitemap.xml 파일 생성은 plugin으로 처리해도 **robots.txt** 파일을 작성해야 한다. 해당 파일에는 웹 크롤러가 내 사이트를 크롤링 시 크롤링할 정책에 대한 설정이 들어간다.
  간단하게 아래와 같이 설정할 수 있다.

  ```Text
  User-agent: *
  Allow: /
  Sitemap: https://im-wali.github.io/sitemap.xml
  ```
  <br/>

# 1-3. Google Search Console sitemap 제출

  * sitemap.xml과 robots.txt를 설정했다면 Google Search Console에 제출한다.
  우선 왼쪽 메뉴에서 **색인 > Sitemaps** 를 클릭한다. 아래와 같은 화면에 sitemap.xml 이라고 입력하고 제출한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-complete-submit-simtemap.png){: .align-center}

  * 정상적으로 Sitemap 제출이 되었다면 아래와 같이 **성공** 이라는 상태가 된다. 다만 색인의 경우 몇일 정도 걸릴 수 있다.

  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-sucess-sitemap.png){: .align-center}
