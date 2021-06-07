---
title:  "Jekyll 테마 선택하기"
search: false
categories:
  - GithubPage
tags:
  - Gihub Page
  - Jekyll
  - 지킬
  - 커스텀마이즈
---

<br/>
# 커스텀 마이즈 하기

  * 지난 시간까지 **Jekyll** 과 **GithubPage** 를 이용해 블로그 만들기 까지 진행했습니다. 하지만 현재로 blog를 포스팅 하기에는 부족한 부분이 많습니다. 이런 부분들을 보완하기 위해서 이번 포스팅 부터는 블로그를 커스텀 마이즈하고 기능들을 추가해 보도록 하겠습니다. 해당 포스팅은 **"minimal-mistakes-master"** 테마 기준이며, 테마에 따라서 설정하는 방법이 다를 수도 있습니다.

# 2. 불필요한 파일 *

  * 처음에 **"minimal-mistakes-master"** 테마를 설치하게 되면 기본적으로 설정된 파일이나, 불필요한 파일까지 따라온다. 이 파일들은 추후 블로그를 커스텀 마이즈할때 필요없는 파일이기 떄문에 삭제하기 하겠다. 다만 **minimal-mistakes-jekyll.gemspec** 파일은 삭제하면 로컬에서 테스트를 할 수 없으니 로컬에서 테스트를 하실 분들은 해당 파일 삭제를 하면 안된다.

![image-center](/assets/images/2021-02-20-delete-file.png){: .align-center}

# 3. 테마 선택

  * 여기 말하는 테마는 Jekyll 테마가 아니라, 자체 테마를 말한다. 현재 **"minimal-mistakes-master"** 은 "air", "aqua", "contrast", "dark", "dirt", "neon", "mint", "plum" "sunrise"이 있으며, 각 화면 은 아래와 같다.

  <br/>
  **air**
  ![image-center](/assets/images/2021-02-20-theme-air.png){: .align-center}

  <br/>
  **aqua**
  ![image-center](/assets/images/2021-02-20-theme-aqua.png){: .align-center}

  <br/>
  **contrast**
  ![image-center](/assets/images/2021-02-20-theme-contrast.png){: .align-center}

  <br/>
  **dark**
  ![image-center](/assets/images/2021-02-20-theme-dark.png){: .align-center}

  <br/>
  **dirt**
  ![image-center](/assets/images/2021-02-20-theme-dirt.png){: .align-center}

  <br/>
  **neon**
  ![image-center](/assets/images/2021-02-20-theme-neon.png){: .align-center}

  <br/>
  **mint**
  ![image-center](/assets/images/2021-02-20-theme-mint.png){: .align-center}

  <br/>
  **plum**
  ![image-center](/assets/images/2021-02-20-theme-plum.png){: .align-center}

  <br/>
  **sunrise**
  ![image-center](/assets/images/2021-02-20-theme-sunrise.png){: .align-center}

# 4. 사이트 제목 및 URL 설정

	**_config.yml에서**
	* tiutle : "블로그 이름"
	* Subtitle : "서브 타이틀"
	* Name : "왼쪽 profile에 기재되는 이름."
	* Description : "사이트 설명"
	* Url : "사이트주소(githubpage)"
	* Repository : "git repository 주소"
	* 시간대 : timezone: Asia/Seoul <br/> -> "jekyll 4.2.0 | Error:  tzinfo" 에러 발생 시 Gemfile 에 "gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw]" 추가.

# 5. Category, tags 세팅

  * 포스팅을 올릴때 태그 혹은 카테고리를 사용하면 관련 포스팅을 모아서 볼 수 있다. **"minimal-mistakes-master"** 의 경우 헤더에 아래의 사진과 같이 추가하면 간단하게 설정 가능하다.

  <br/>
  ![image-center](/assets/images/2021-02-20-catogry-tags.png){: .align-center}
