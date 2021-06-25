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
  ![image-center](/assets/images/2021-03-22-google-search-console.png){: .align-center}

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

  * Google 검색 창에서 **site:Im-wali.github.io** 으로 검색하면 등록된지 확인 가능하다.
  <br/>
  ![image-center](/assets/images/2021-03-22-google-search-console-search-site.png){: .align-center}


# 2. Naver
  * Github Page로 블로그를 만드는 경우 제일 많은 유입 경로가 Google일 것이다. 하지만 국내에서 제일 많이 쓰는 포털이 Naver를 버리기에는 아쉬움이 많다. 그래서 Naver Search Advisor(웹마스터 도구)를 통해 Naver 검색 내 블로그가 검색될 수 있게 해보겠다.

# 2-1. Naver Search Advisor(웹마스터 도구)
  * Naver Search Advisor는 운영하고 있는 사이트의 검색을 위한 색인 및 검색 반영 현황을 모니터링하고 관리 가능하도록 하는 Naver에서 제공하는 도구 이다.

# 2-1. Naver Search Advisor  웹
  * Naver Search Advisor를 사용하기 위해서는 아래 URL를 통해 우선 사이트를 이동하여 로그인 해야 된다. 로그인 한 후 우측 상단의 "웹마스터 도구"를 클릭한다.

  * 사이트 주소 : <a href="https://searchadvisor.naver.com/" target="_blank">https://searchadvisor.naver.com/</a>
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor.png){: .align-center}


  * 웹마스터 도구 화면으로 넘어가면 이와 같이 사이트 등록할 수 있는 화면이 출력된다. 여기에 자신의 블로그 URL를 입력 해주면 된다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor-insert-url.png){: .align-center}

  * 웹마스터 도구 화면으로 넘어가면 이와 같이 사이트 등록할 수 있는 화면이 출력된다. 여기에 자신의 블로그 URL를 입력 해주면 된다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor-insert-url.png){: .align-center}


  * URL를 등록하면 사이트 소유확인을 해야 된다. 아래와 같이 HTML 파일을 루트에 업로드 하는 방식과 <head> 섹션에 태그를 삽입함으로 소유 확인하는 방식 두가지 있는데, 필자는 파일이 많아지는 것이 싫어 <head> 섹션에 삽입하였습니다. **_includes/head.html** 파일 상단에 아래와 같이 입력하면 된다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor-auth-site.png){: .align-center}

  ```html
  <!-- https://t.co/dKP3o1e -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="naver-site-verification" content="7c499f3a7e38fefaa200e68df4dc1d88d42dbd3f" />
  ```

  * 이와 같이 사이트 소유 확인 끝나면, 이전에 작성한 sitemap을 등록해 주면 된다. 우측 메뉴에서 **요청 > 사이트맵 제출** 로 이동한다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor-menu-sitemap.png){: .align-center}

  * simtemap 등록은 어려운게 없다. 그냥 URL 뒤에 sitemap.xml 이라고 입력하고 "확인" 버튼만 클릭하면 된다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-insert-sitemap.png){: .align-center}

  * sitemap 등록했다면 웹 페이지 수집을 요청해야 한다. **요청 > 웹 페이지 수집** 메뉴로 이동한다. 필자의 블로그의 경우 하위 주소가 없기 때문에 아무것도 입력하지 않고 바로 "확인" 버튼을 클릭하여 수집 요청을 했다.
  <br/>
  ![image-center](/assets/images/2021-03-22-naver-search-advisor-insert-page-url.png){: .align-center}

  * Naver에도 등록이 완료되었다. 다만 네이버에서 블로그의 페이지를 인식하는데는 시간이 걸리기 때문에 그전까지 열심히 포스팅하면서 기다리면 된다.

# 3. Daum
  * 다음의 경우 Google과 Naver와 다르게 소유 확인도 없이 URL만 등록하면 끝이다. 그래서 크롤링이나 검색 제외 등의 기능을 제공 하지 않는다. 아래 URL로 이동하여 URL를 등록하면되며, 등록 시 필요한 것은 정보 수집 동의와 이메일 정보만 입력하면 된다.

  * 사이트 주소 : <a href="https://register.search.daum.net/index.daum" target="_blank">https://register.search.daum.net/index.daum</a>
  <br/>
  ![image-center](/assets/images/2021-03-22-daum-insert-searchurl.png){: .align-center}

# 4. 끝마치며
  * 이것으로 각종 포털 사이트에서 내가 만든 블로그를 검색할 수 있게 되었다. 블로그 지속적으로 운영하면서 계속 수정을 하겠지만, 지금까지 올려놓은 Github Page 블로그 관련 포스팅으로 기본적인 설정들은 다 할 수 있을것이다. 이 다음 포스팅 부터는 기술적인 관련된 내용을 정리하여 포스팅할 예정이다. 
