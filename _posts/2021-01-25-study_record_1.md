---
title: "[Django] Cookiecutter를 이용한 django 시작하기"
categories:
  - Django
tags:
  - 웹개발
  - cookiecutter
  - django
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## Django(장고)를 시작하는 방법
### 1. django-admin 에서 startproject를 이용(기본)

```{.python}
django-admin startproject mysitename
```
 - 이 방법은 거의 모든 장고 Tutorial에 소개된 방법으로, 익숙한? 방법이라고 볼 수 있다.
 - 다만, 애플리케이션의 덩치가 커짐에 따라 복잡도가 올라가는 문제가 있다고 한다.
 - 그래서 수많은 장고 유저들이 고민하고, 그중 뛰어는 일부가 고안해낸 일종의 종합세트 개념의 Tool이 바로 2번에서 소개되는 방법이다.

### 2. cookiecutter 사용하기
~~~{.python}
# 1)쿠키커터 설치
pip install cookiecutter

# 2)프로젝트 시작
cookiecutter https://github.com/pydanny/cookiecutter-django
~~~

 - 프로젝트를 시작하게 되면 프로젝트 이름, 사용할 오픈라이센스, postgresql 버전 등 여러개를 물어보고 알아서 구성해준다.
 - 만약, 잘 모르겠다 하면 그냥 엔터를 쳐서 default 값으로 입력해도 무방하다. 모든 건 추후 변경이 가능하니깐.
 - 쿠키커터를 사용할 경우 기본적으로 설치되어야할 라이브러리들이 있는데, 이는 아래 명령어를 통해 쉽게 설치가 가능하다.
  
~~~{.python}
pipenv install -r requirements/local.txt
~~~
