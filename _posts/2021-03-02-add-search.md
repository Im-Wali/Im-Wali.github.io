---
title:  "검색 & CI 기능 추가"
search: false
categories:
  - GithubPage
tags:
  - Gihub Page
  - Jekyll
  - 지킬
  - 검색
  - Travis CI
---

<br/>
# 검색 & CI 기능 추가(Algolia, Travis-ci)
  * 블로그에서 게시된 글을 검색하는 기능을 수동으로 추가해줘야 한다. ***"minimal-mistakes-master"*** 의 경우 "Lunr", "Algolia", "Google Custom Search Engine", "Google Search Console"로 검색 기능을 추가할 수 있다. 이중에 금일 포스팅에서 **"Algolia"** 을 통해 검색 기능을 추가해보겠다. 추가적으로 Travis CI를 통한 CI 기능도 추가해보도록 하겠습니다.

# 1. Algolia

  * Algolia는 웹 사이트의 콘텐츠를 색인화하여 저장하고 색인화된 데이터를 기반으로 검색 기능을 제공해주는 서비스이다.  SaaS 플랫폼으로서 검색 서비스 플랫폼이다. 다양한 환경에 대한 API를 제공하고 있다.
  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-logo.png){: .align-center}

## 1-1. 회원가입하기
  * 우선 제일 먼저 할일은 역시나 회원가입이다. 아래 링크로 통해 사이트를 이동하여 우측 상단의 "Start Free"를 클릭하고 다음 페이지에서 "Sign up with Github"를 클릭하여 회원가입을 한다.
  <br/>
  * 사이트 주소 : <a href="https://disqus.com/" target="_blank">https://disqus.com/</a>
  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-start-free.png){: .align-center}
  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-signup.png){: .align-center}

  <br/>
  * 이때 데이터 센터를 선택하라는 화면이 있는데 제일 가까운 일본을 선택하면 된다.

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-signup-select-datecenter.png){: .align-center}

## 1-2. 기본 설정하기
  * 처음으로 로그인 해서 billing 메뉴로 가면 현재 선택중인 가격 정책이 보인다. 이를 Free로 변경 해준다.  

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-signup-select-plan.png){: .align-center}

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-select-price.png){: .align-center}

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-signup-select-plan2.png){: .align-center}

## 1-3. 인덱스 추가 하기
  * 이제 부터는 검색 기능을 추가하기 위해 인덱스 생성을 해보겠다. 우선 "Indices" 메뉴로 이동하여 "Create Index"를 클릭하고 index name을 입력하여 index를 생성한다.
  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-create-index.png){: .align-center}

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-create-index2.png){: .align-center}

## 1-4. API 키 확인 하기
  * 이제 API Key 값을 통해 현재 Githubpage 블로그와 연동해 보겠다. 우선 "API Keys" 메뉴로 이동하여 현재 어떠한 Key 값이 있는 확인한다.

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-site-api-key.png){: .align-center}


## 1-5. _config.yml 파일 수정
  * 우선 _config 파일의 search 부분을 true로 변경해준다. 또한 search_provider를 algolia로 입력해주고 algolia의 API 값을 설정해 준다.

  ```ruby
  search                   : true # true, false (default)
  search_full_content      : true # true, false (default)
  search_provider          : algolia # lunr (default), algolia, google
  algolia:
    application_id         : CJTASDASDWZGE # YOUR_APPLICATION_ID
    index_name             : im-wali # YOUR_INDEX_NAME
    search_only_api_key    : 6a0f91231236e29a86615dc14 # YOUR_SEARCH_ONLY_API_KEY

  ```
  <br/>

## 1-5. Gemfile
  * Algolia를 사용하기 위한 package(?)를 설치하기 위해 Gemfile에 맨 아래(gemspec 명령어 바로 위) 내용을 추가한다.

  ```ruby
  group :jekyll_plugins do
    gem "jekyll-paginate"
    gem "jekyll-sitemap"
    gem "jekyll-gist"
    gem "jekyll-feed"
    gem "jemoji"
    gem "jekyll-include-cache"
    gem "jekyll-algolia"
  end    

  gemspec
  ```
  <br/>
## 1-6. 검색하기
  * 위에 내용을 쭉 진행했다면 해당 내용들을 적용하면 아래와 같이 검색할 수 있다.

  <br/>
  ![image-center](/assets/images/2021-03-01-algolia-search-use-case.png){: .align-center}  


# 2. Travis CI
  * ***Travis CI는 호스팅 지속적 통함(CI)의 서비스의 하나로서 Github에 호스팅되는 소프트웨어 프로젝트의 빌드, 테스트를 위해 사용한다. (위키백과)*** 이와 같이 Travis CI는 Github에서 호스팅 하는 프로젝트를 빌드, 테스트하기 위하 CI 툴로서 Github와 호환이 잘되기 떄문에 간단하게 설정하여 사용할 수 있다. Travis CI를 사용하면 자신이 수정한 소스가 빌드되는 과정을 볼 수 있으며 에러가 나는 경우 로그도 확인할 수 있다. Github page로 블로그를 한다면 필수적으로 사용해야되는 기능이라고 생각한다.

## 2-1. Travis CI 회원 가입 하기
  * 우선 아래 링크를 통해 사이트로 이동하여 회원 가입을 진행한다. github의 Repository에 접근해야 되기 때문에 Github 아이디로 회원 가입한다.

  <br/>
  * 사이트 주소 : <a href="https://travis-ci.org/" target="_blank">https://travis-ci.org/</a>

  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-main.png){: .align-center}

## 2-2. Github Repository 설정
  * 로그인 후 우측 상단의 "setting" 버튼을 통해 설정 페이지로 이동한다.

  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-setting.png){: .align-center}

  <br/>
  * 세팅 화면에서 "Manage repositories on GitHub" 을 클릭하여 Github 설정 페이지로 이동한다.
  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-setting-repository.png){: .align-center}


  <br/>
  * Repository access를 All repositories를 선택하여 Travis CI에서 모든 Repository에 접근할 수 있게 설정한다.
  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-setting-all-repository.png){: .align-center}

## 2-3. API Key 설정
  * 로그인 후 우측 상단의 "setting" 버튼을 통해 설정 페이지로 이동하여 Githupage Repository의 "Settings"를 클릭한다.

  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-setting-api01.png){: .align-center}

  * "Enviroment Variables"에 ALGOLIA_API_KEY을 Name으로 하고 Value로 Algolia의 Admin API Key 값을 넣어준다.

  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-setting-api02.png){: .align-center}

## 2-4. 사용법
  * 사용법은 기존에 사용하는 방식으로 포스팅하면 자동으로 빌드가 되기 때문에 테스트를 해볼 분들은 현재 수정한 소스를 Push해보면 아래와 같은 화면을 볼 수 있다. 만일 빌드 중 에러가 발생하면 친절하게 github 계정으로 이메일이 발송된다. 이와 같은 기능 때문에 Github Page를 쓰는 분이라면 꼭 추가해야되는 기능이다.

  <br/>
  ![image-center](/assets/images/2021-03-01-travis-ci-use-case.png){: .align-center}
