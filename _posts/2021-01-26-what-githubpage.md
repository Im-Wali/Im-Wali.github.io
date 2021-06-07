---
title:  "Github Page 란?"
search: false
categories:
  - GithubPage
tag:
  - GithubPage
  - Githunb
  - Github page 란?
  - Github Desktop
last_modified_at: 2021-01-17T08:00:34-05:00
---

# 서론
*****
해당 포스트는 github page로 블로그를 만드는 방법에 대한 첫번째 포스트 이다.
티스토리, 워드프레스, 브런치 등 다양한 블로그들이 있지만 내가 선택한 블로그는 **Github Page + Jekyll** 이다.
댜앙한 이유들로 인해서 **Github Page + Jekyll**을 선택했는데 이유들은 포스팅을 통해 천천히 설명하겠다.




## 1. Github Page란?

![image-center](/assets/images/2021-01-26-what-githubpage_github-pages.png){: .align-center}



### 1-1. Github
*****

 Github Page를 앞서 우선적으로 Github가 무엇인지 설명이 필요하다. Github란 Git을 조금더 편하게 이용하도록 만든 Git 서버 호스팅 서비스이고,
 오픈소스 소프트웨어의 중심(Hub) 역할을 하면서 오픈소스 프로젝트가 널리 퍼지는데 크게 기여하고 있는 서비스이다.<br/>
 조금더 쉽게 설명하자면 Git은 형상 관리 도구(Configuration Management Tool)로서 한마디로 소스를 관리해주는 툴이라고 생각하면 되고, 이를 조금더 편하게 사용하기 위한것이 Github라고 생각하면 된다.
 이 Github는 개발자 혹은 IT를 하는 사람들은 꼭 필수적으로 사용해야되는 것이니 꼭 기억해두는것이 좋다.


### 1-2. Github Page 란?
*****

Github Page는 위에 설명한 Github에서 제공하는 정적 사이트 호스팅 서비스로 일반적인 HTML 콘텐츠를 지원하는 것 이외에도 인기있는 정적 사이트 **(Static Web Site)** 생성기인 Jekyll을 지원한다.
Github Page로 작성된 blog를 Github에서는 무료로 호스팅 해준다. 호스팅 하는 URL은 보통 https://username.github.io 형태로 구성된다.

![image-center](/assets/images/2021-01-26-what-githubpage_service_architecture.png){: .align-center}



위에 이미지에서 처럼 사용자가 PC에 구성한 Local Repository에 Github의 Remote Repository로 Push 하면 Github에서 https://username.github.io 으로 무료로 호스팅해줘서 일반 사용자들이 블로그에 방문할 수 있다.


### 1-3. Github Page 장/단점
장/단점을 설명하기 전에 앞서 아래 장/단점은 저의 주관적인 의견이라는 것을 말씀드립니다.

* 장점
  - **무료이다.**<br/>
    우선 위에 얘기했던 대로 Github에서 무료로 웹 호스팅을 해주기 때문에 무료로 이용이 가능하다. 다만, Jekyll 테마에 따라 비용이 발생할 수 있다.

  - **개발자 친화적이다.**<br/>
    Github Page는 Jekyll와 마크다운을 지원하며, 개발자에게 친숙한 Github를 사용하기 때문에 개발자가 접근하기 좋은 블로그이다.

  - **가볍다.**<br/>
    정적 사이트이기 때문에 빠르다.

  - **커스텀 마이즈에 대한 자유도가 높다.**<br/>
    Jekyll의 테마를 선택할 수 있으며, 디자인이나, CSS 등 직접 수정할 수 있기 떄문에 커스텀 마이즈에 대한 자유도가 높다.


* 단점
  - **어렵다.**<br/>
    초기에 설정할때 엄청난 어려움을 겪는다. 우선 개발자가 아닌 사람에게는 거의 벽의 가깝다고 생각한다. 물론 간단 IT 지식을 가진 사람이라면 끈기만 있다면 충분히 할 수 있다.

  - **포스팅할때 시간이 오래 걸린다.**<br/>
    지금까지 포스팅을 하면서 느낀 부분이 다른 위지윅 에디터를 지원하는 블로그에 비해 포스팅을 작성하는 시간이 오래 걸린다.

  - **기본적인 기능들을 추가로 설정 해야한다.**<br/>
    댓글 기능, 검색 기능 등 다른 블로그에서 기본적으로 제공되는 기능들이 없다. Third Party를 통해 추가로 설정하여 사용해야 된다.

## 2. Github Page 시작하기
 이제부터 Github Page를 구성하기 위한 첫단계로 Github를 가입하고 Local에 Repository를 구성해보겠다.

### 2-1. Github 회원가입/로그인 하기
Github Page로 blog를 만들기 위해서는 우선 Github 계정이 있어야 한다.
<https://github.com/>로 이동하여 아래와 같은 화면을 볼수 있다. 아래에서 "Sign up"을 클릭 하면 회원가입 페이지로 이동한다.
계정이 있으면 바로 "Sign in"으로 로그인하면 된다.


![image-center](/assets/images/2021-01-26-github-mainpage.png){: .align-center}


Username, Email address, paassword 입력하여 회원가입하면 된다.


![image-center](/assets/images/2021-01-26-github-join.png){: .align-center}


로그인 하면 아래와 같은 화면을 볼 수 있다.


![image-center](/assets/images/2021-01-26-github-login_first_page.png){: .align-center}



### 2-2. Repository 생성하기
Github 로그인 까지 완료 했다며, Github Page를 만들기 위한 공간을 생성해야된다. Resitory는 왼쪽 상단의 "New" 버튼을 클릭하여 생성할 수 있다.
![image-center](/assets/images/2021-01-26-github-new-repository.png){: .align-center}


Repository Name과 Description을 작성하는데 이때 Repository Name은 User Name으로 하는것이 좋다. 왜냐하면 나중에 Github Page를 호스팅 할때 "https://{username}.github.io"로 되기 때문에 여기서 Repository Name를 User Name과 동일하게 안하면 위와 같은 URL로 호스팅 하지 못한다. <br/>
그리고 public을 선택한다. Repository를 공개하겠다는 의미이다. 참고로 예전에는 Private이 유료이었지만 현재는 부분적으로 무료로 사용할 수 있다.<br/>
나머지는 그냥 선택하지 않고 "Create repository"를 클릭하여 Repository를 생성하면 된다.
![image-center](/assets/images/2021-01-26-github-create-repository.png){: .align-center}


아래와 같이 생성된 화면을 볼 수 있다.
![image-center](/assets/images/2021-01-26-github-first-repository.png){: .align-center}


### 2-3. Github Desktop 다운로드
이제부터 로컬 PC에 2-4에서 생성한 Remote Repository를 복사하여 Local Repository를 구성할려고 한다. 이때 Github Desktop이라는 프로그램을 사용하면 시각적으로 편하게 구성할 수 있다.
<https://desktop.github.com/> 해당 링크로 가서 다운로드 받으면 된다.
![image-center](/assets/images/2021-01-26-github-desktop-download.png){: .align-center}


Github Desktop을 설치하여 실행하면 아래와 같은 화면이 된다.
![image-center](/assets/images/2021-01-26-github-desktop.png){: .align-center}


우선 Remote Repository를 복사하기 위해서는 Github desktop에 로그인 정보를 입력해야 한다. 우선 Github Desktop의 왼쪽 상단의 "File > option"을 클릭한다.
![image-center](/assets/images/2021-01-26-github-desktop-option.png){: .align-center}


Options에서 Account 탭에서 "Sign In"을 클릭하고 "Continue with browser" 버튼을 클릭하여 현재 Chrome에 저장되어 있는 Github 계정정보를 가지고 온다.
![image-center](/assets/images/2021-01-26-github-desktop-signin.png){: .align-center}


![image-center](/assets/images/2021-01-26-github-desktop-Continue with browser.png){: .align-center}

### 2-4. Local Repository 구성하기
2-2에서 생성한 Repository page에서 HTTP 링크를 복사한다.
![image-center](/assets/images/2021-01-26-github-repository-httpl.png){: .align-center}


Github Desk에서 "File > Clone Repository" 클릭 하여, "URL" 탭에 복사한 HTTP 링크를 입력하고 "Clone"을 클릭하여 Remote Repository로 Local Repository 구성한다.
![image-center](/assets/images/2021-01-26-github-clone-repository_02.png){: .align-center}


![image-center](/assets/images/2021-01-26-github-clone-repository.png){: .align-center}


아래와 같이 로컬 환경에 Repository가 생성된것을 볼 수 있다.


![image-center](/assets/images/2021-01-26-github-rocal-repository.png){: .align-center}


다음 포스팅에서는 Local Repository에 Jekyll 환경을 구성하겠다.
