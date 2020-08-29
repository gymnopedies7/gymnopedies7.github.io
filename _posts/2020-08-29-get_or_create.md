---
title: "Django objects.get_or_create "
categories:
  - Django
  - 웹개발
tags:
  - 웹개발
  - Web
  - objects
  - get_or_create
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---

## get_or_create 의미
  - get_or_create는 구하고자 하는 객체가 이미 존재하는 지에 대한 정보를 얻는데 유용하다(객체 조회)
  1) 구하고자 하는 객체가 존재할 경우 객체를 얻고(get)
  2) 객체가 존재하지 않을 경우 생성을 한다(create)

## get_or_create 사용예제 
~~~
object, flag = A.objects.get_or_create(name=name, code=code)
~~~
 - 이 메서드는 (object, created)라는 튜플형식으로 반환되며
 - object는 꺼내려고 하는 모델의 인스턴스를 반환,
 - created는 boolean의 flag이며,True/False로 반환한다.

### 반환결과
    - 인스턴스가 기존에 존재해서 Database에서 꺼내올 경우 : False
    - 인스턴스가 기존에 없어서, 신규로 생성된 경우 : True