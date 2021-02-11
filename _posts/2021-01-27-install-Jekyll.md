---
title:  "Jekyll이란?"
search: false
tag:
  - Jekyll
last_modified_at: 2021-01-27T08:00:34-05:00
---


# 1. Jekyll 이란?
  ![image-center](/assets/images/2021-01-27-jekyll-logo.png){: .align-center}
  이번은 Jekyll에 대해서 포스팅 할려고 한다. 이전 <a href="/what-githubpage">포스트</a>에서 말했듯이 github page로 블로그를 할려면 Jekyll을 사용해야된다.
  Jekyll은 개인, 프로젝트 또는 조직 사이트를 위한 간단한 정적 사이트 생성기이다. 지킬을 이용하면 HTML & Javascript, Markdown 그리고 Liquid(Ruby로 작성된 오픈소스 템플릿 언어)으로 Static Web Site를 만들 수 있다.


**Static Web Site VS Dynamic Web Site**
  * Static Web Site 동작 과정 : <br/>
    사용자가 웹 서버로 요청 하면 서버는 미리 저정된 파일들 중 사용자가 요청한 페이지를 응답한다.
  * Dynamic Web Site 동작 과정 : <br/>
    사용자가 웹 서버로 요청하면 웹 서버는 HTML이나 이미지를 처리하고, 동적 데이터를 나타내기 위한 DB연동을 WAS에 처리 요청을 한다. WAS는 웹 서버로 동적 데이터의 처리 결과를 응답하고 웹 서버는 이렇게 동적으로 구성된 페이지를 HTML로 사용자에게 응답한다.



**Markdown 언어 란?** <br/>
  마크업 언어란 문서에 부가적인 정보를 표시하기 위해 고안된 언어이다. 마크 다운은 마크업의 문법을 조금 더 쉽게 바꾼것이다. 텍스트 기반의 마크언어로 2004년 존 그루버에 의해 만들어졌으며 쉽게 쓰고 읽을 수 있으며 HTML 로 변환이 가능하다. 특수기호와 문자를 이용한 매우 간단한 구조의 문법을 지원하며, 빠르게  콘텐츠를 작성할 수 있다.

# 2. Jekyll 설치.
* Windows 10 환경에서 Jekyll을 실행할 수 있는 환경을 구성하겠다.

## 2-1. Ruby & Dev Kit 설치
* 위에서 얘기했듯이 Jekyll은 Liquid를 지원하기 위해서 Ruby는 필수적으로 필요하다. <a href="https://rubyinstaller.org/downloads">https://rubyinstaller.org/downloads</a>으로 이동하여 "Ruby+Devkit 2.5.8-2 (x64)"를 선택한다.
![image-center](/assets/images/2021-01-27-ruby-devkit-install.png){: .align-center}

* "I accept the License" 클릭 후 "Next" 버튼을 클릭한다.
![image-center](/assets/images/2021-01-27-ruby-devkit-install-01.png){: .align-center}

* 그후로 다른 설정 필요없이 "Next" 버튼 을 클릭하여 다운로드 받는다.
![image-center](/assets/images/2021-01-27-ruby-devkit-install-02.png){: .align-center}

* windows 키를 클릭하여 "ruby"를 입력하여 Ruby가 설치 된것을 볼 수 있다. "Start Command Prompt With Ruby"을 클릭 하여 실행한다.
![image-center](/assets/images/2021-01-27-ruby-devkit-install-03.png){: .align-center}


# 3. Jekyll 사용법
* 윈도우 환경에서는 인코딩으로 인해 오류가 발생할 가능성이 있으니 `chcp 65001`을 입력하여 인코딩을 지정해 준다.
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-01.png){: .align-center}
<br/>
```ruby
chcp 65001
```

* 이전 <a href="/what-githubpage">포스트</a>에서 구성한 Local Repository로 이동한다.
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-02.png){: .align-center}
<br/>
```ruby
cd "localRepository 위치"
```

* gem을 통해 jekyll과 bundler를 설치한다.
<br/>
```ruby
gem install jekyll bundler
jekyll new im-wali1
cd im-wali1
bundle exec jekyll serve
```
<br/>
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-03.png){: .align-center}
<br/>
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-04.png){: .align-center}
<br/>
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-05.png){: .align-center}
<br/>
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-06.png){: .align-center}



* 'bundle exec jekyll serve' 를 실행하면 브라우저를 통해 "http://localhost:4000"으로 이동하면 아래와 같은 화면을 볼 수 있다.
![image-center](/assets/images/2021-01-27-start-command-prompt-with-ruby-07.png){: .align-center}


# 4. Github page로 호스팅 하기
* 지금까지 로컬 환경에서 Jekyll 샘플 블로그를 만들었다. 지금까지 만든 결과물을 github page의 무료 호스팅 기능을 통해 호스팅 해보겠다.

* 우선 지금까지 만든 결과물을 커밋한다. github desktop을 통해 결과물을 "commit"하고 이를 "push"를 통해 github remote repository에 적용한다.
<br/>
![image-center](/assets/images/2021-01-27-github-page-hosting.png){: .align-center}

* github 사이트로 이동하여 해당 Repository에서 "Settings"를 클릭한다.
<br/>
![image-center](/assets/images/2021-01-27-github-page-hosting-01.png){: .align-center}

* 'Options'에서 하단으로 조금 내려가다 보면 'Github Pages'라는 곳에서 'Note'라고 되어 있는 부분을 'Master'로 선택하고 'Save' 버튼을 클릭한다.
<br/>
![image-center](/assets/images/2021-01-27-github-page-hosting-02.png){: .align-center}


* 'Save' 하면 아래와 같이 설정되어 있는것을 볼 수 있다. 여기서 생성된 링크로 이동하면 로컬에 세팅한 샘플 블로그를 볼 수 있다.
<br/>
![image-center](/assets/images/2021-01-27-github-page-hosting-03.png){: .align-center}

# 5. Liquid 사용법
- 지금까지 github page와 Jekyll로 샘플 블로그를 만들어 봤다. 이제부터 테마 선택과 커스텀 마이즈에 대해서 포스팅 할 것인데 그전에 알아 되는 것이 있다.
바로 Liquid라는 것이다. 이 부분이 일반적인 HTML이나 Javascript와 다르게 ruby를 기반으로 하기 떄문에 익숙하지 않다. 그래서 간단하게 Liquid가 무엇인지와 구성요소에 대해서 설명할려고한다. 
해당 내용들은 <a href="https://jekyllrb-ko.github.io/docs/">Jekyll Docs</a>에서 가지고 왔다. 궁금한 부분이 더 있다면 해당 링크로 이동해서 확인해보면 될거 같다.

* Liquid는 템플릿 언어로서 세 가지 부분으로 나눌 수 있다. 세가지는 오브젝트와 태그, 필터이다.
* 오브젝트<br/>
  오브젝트는 컨텐츠를 어디에 출력할지 liquid에 알려준다. 두 개의 중괄효로 표시된다.
  ```liquid
  {% raw %}{{ page.title }}{% endraw %}
  ```


* 태그 <br/>
  태그는 템플릿의 논리 연산과 흐름을 제어한다. 중괄호와 퍼센트 문자로 표시한다. {% raw %}{%{% endraw %}  와 {% raw %}%}{% endraw %} 로 표시.

  ```liquid
  {% raw %}{% if page.show_sidebar %}{% endraw %} 
    {% raw %}<div class="sidebar"> sidebar content </div> {% endraw %} 
  {% raw %}{% endif %}{% endraw %}
  ```


* 필터<br/>
  필터는 Liquid 오브젝트의 출력을 변화 시킨다. | 로 구분해서 오브젝트 안에 사용한다.
  ```liquid
  {% raw %}{{ "hi" | capitalize }}{% endraw %}
  ```