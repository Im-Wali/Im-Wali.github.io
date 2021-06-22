---
title:  "구글 Analytics 기능 추가"
search: false
categories:
  - GithubPage
tags:
  - Gihub Page
  - Jekyll
  - 지킬
  - Google Analytics
---

<br/>
# 구글 Analytics 기능 추가하기
  * 블로그에 들어오는 방문자에 대한 분석을 하기 위해서는 Google analytics를 연동해줘야 된다. 이를 통해 방문자에 대한 분석 및 추적을 할 수 있어 블로그를 운영하는데 많은 도움이 된다.

# 1. Google Analytics

  * 구글 애널리틱스(Google Analytics)는 현재 구글 마케팅 플랫폼 브랜드 내의 플랫폼으로서, 웹사이트 트래픽을 추적하고 보고하는 구글이 제공하는 웹 애널리틱스 서비스이다.

  * google analytics의 장점은 무료라는 것이다. 월간 조회수에 따라 한도가 있기는 하지만 개인 블로그를 하기에는 충분한 용량이기 때문에 무료라고 봐도 무방하다. 또 다른 장점으로는 다양한 기능 제공이다. 시각적으로 정보를 잘 보여주며, 다양한 목표 설정 등 다양한 기능을 제공한다. 다만 단점으로는 많은 정보와 기능들을 내포하고 있기 때문에 사용하는데 있어서 익숙해지는 시간이 필요하다.

  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics.png){: .align-center}

# 2. Google Analytics 기본 설정하기
 * 우선 Google Analytics을 설정하기 위해서는 우선 아래 URL로 이동하여 회원가입 혹은 로그인을 한다.

 * 사이트 주소 : <a href="https://analytics.google.com/analytics/web/provision/#/provision" target="_blank">https://analytics.google.com/analytics/web/provision/#/provision</a>

 * 메인 페이지에서 "측정 시작" 버튼을 클릭한다.
 <br/>
 ![image-center](/assets/images/2021-03-12-google-analytics-main-site.png){: .align-center}


  * 계정 정보를 입력한 후 "다음"버튼을 클릭한다. 이 계정를 토대로 정보가 관리된다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-setting-account.png){: .align-center}

  * 속성 명을 입력한다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-setting-attribute.png){: .align-center}


  * 비지니스 정보를 입력한다. 개인 블로그로 이용할 예정이기 때문에 아래 사진과 같이 입력했다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-setting-business.png){: .align-center}

# 2. Google Analytics와 Github Page 연동하기

  * 앞서 Google Analytics에 회원가입하고, 기본적인 설정을 했다. 이제는 Github Page와 연동하는 방법에 대해서 알아보겠다.

  * 우선 관리자 페이지에서 속성에서 "데이터 스트림"을 선택한다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-setting-datastream.png){: .align-center}

  * 우리는 Github Page와 연결할거니까 "웹"을 선택한다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-select-data-stream.png){: .align-center}

  * 현재 Github Page 링크와 별명으로 사용할 이름을 입력한다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-insert-website-url.png){: .align-center}

  * 데이터 스트림을 만들면 아래와 같이 추적ID가 생성이 된다. 이를 복사해서 **_config.yml** 파일에 입력해준다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-trace-id.png){: .align-center}

  <br/>

  ```ruby
  # Analytics
  analytics:
    provider               : "google-gtag" # false (default), "google", "google-universal", "google-gtag", "custom"
    google:
      tracking_id          : "G-Q8XPW2ZMZ0"
      anonymize_ip         : false # true, false (default)
  ```
  <br/>


  * 이제 설정이 완료되었다. 아래 처럼 블로그에 접근한 사람에 대한 정보를 볼 수 있다.
  <br/>
  ![image-center](/assets/images/2021-03-12-google-analytics-complete.png){: .align-center}
