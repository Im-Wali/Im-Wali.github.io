---
title:  "Disqus로 댓글 기능 추가하기"
search: false
categories:
  - GithubPage
tags:
  - Gihub Page
  - Jekyll
  - 지킬
  - Disqus
  - 댓글
---

<br/>
# 댓글 기능 추가.

  * 지난 시간에 이어 *GithubPage* 블로그를 커스텀 마이즈할려고 한다. 금일 포스트에서는 Disqus를 통해 블로그에 댓글 기능을 추가해보도록 하겠다.

# 1. Disqus

  * Disqus란 소셜 댓글 서비스의 하나이다. 소셜 댓글 서비스란 소설미디어(SNS)를 활용한 댓글 시스템으로 SNS와 연동하여 댓글을 달 수 있게 해주는 서비스이다. 다른 계정이 필요 없이 SNS 계정만 있으면 댓글을 달 수 있기 때문에 사용자 편의성 측면에서도 좋다. 그리고 **"minimal-mistakes-master"** 에서는 추가적으로 설치해야되는 파일 없이 계정 등록과 설정만 수정하면 바로 댓글 기능을 추가할 수 있다.


# 2. Disqus를 통한 댓글 기능 추가

  * Disqus를 통해 댓글 기능을 추가하고 싶다면 아래와 같은 순서로 진행하면 된다.

## 2-1. Disqus 회원가입

  * 우선 사이트로 이동하면 아래와 같은 화면을 볼 수 있다. 여기서 우측 상단의 "Get Started" 버튼을 클릭하여 회원 가입 페이지로 이동한다.
  <br/>
  * 사이트 주소 : <a href="https://disqus.com/" target="_blank">https://disqus.com/</a>
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-main.png){: .align-center}
  <br/>

  * 아래와 같은 화면에서 회원 가입을 진행한다. 필자의 경우는 Google 계정을 통해 회원가입을 했다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-signup.png){: .align-center}

## 2-2. Githupage 블로그 등록하기

  * 로그인 후에 profile의 클릭하면 "Home"이라는 부분 클릭한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-home.png){: .align-center}

  * 페이지 이동 후 우측 상단의 설정 버튼에서 "Add Disqus To Site"을 클릭한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-setting.png){: .align-center}

  * 페이지 맨 하단의 "GET STARED"을 클릭한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-get-started.png){: .align-center}

  * "I want to sintall Disqus on my site"를 클릭한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-install.png){: .align-center}

  * "Website Name"과 Category, Language를 선택한다. 참고로 한글이 없기 때문에 English를 선택한다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-create-new-site.png){: .align-center}

  * 가격 정책을 선택한다. 이때 밑에 자세히 보면 Basic이라고 되어 있다. 이 basic을 선택하면 된다. basic을 선택하면 따로 금액 결제는 없다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-basic.png){: .align-center}

  * "Jekyll"을 선택하고, 다음 페이지에서 입력할 필요없이 configure을 클릭하여 넘어 간다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-button-jekyll.png){: .align-center}

  * 아래와 같이 입력하고 "next" 후 이후 설정에서 입력하거나 선택할 필요 없으니 그냥 스킵 또는 complete 하면된다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-setting-site.png){: .align-center}

  * 설정이 완료되면 좌측 상단에 아래와 같은 정보를 확인할 수 있다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-complete-new-site.png){: .align-center}

## 2-3. Disqus 설정
  * _config.yml 파일에서 shortName을 변경해줘야 된다.

  ```ruby
  comments:
  provider: "disqus"
  disqus:
  shortname: "your-disqus-shortname"
  ```
  <br/>

  * 추가로 맨밑에 "defaults"에 comments를 true변경해줘야 된다.
  
  ```ruby
  defaults:
  - scope:
      path: ""
      type: posts
    values:
      layout: single
      author_profile: true
      read_time: false
      comments: true
      share: true
      related: true
      show_date: true
  ```
  <br/>

## 2-4 댓글 적용 화면
  * 위와 같이 진행하면 아래와 같은 화면처럼 적용된것을 볼 수 있다.
  <br/>
  ![image-center](/assets/images/2021-02-26-disqus-comments.png){: .align-center}
