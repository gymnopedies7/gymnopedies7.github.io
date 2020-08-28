---
title: "Django Migration Error"
categories:
  - Django
  - 웹개발
tags:
  - 웹개발
  - Web
  - migrate
  - migration
  - 맥북
  - OSX
  - error
  - column length
  - 1074
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---

## Django Migration 오류발생
  - Migration 시 모델을 잘못작성했을 경우 최초 마이그레이션에 기록이 남아  
    아무리 수정해도 똑같이 에러가 발생되는 경우
  ~~~
    MySQLdb._exceptions.OperationalError: (1074, "Column length too big for column 'code' (max = 16383); use BLOB or TEXT instead")
  ~~~

### 해결책 
 - 이전에 마이그레이션된 내용과 충돌 할 수 있으므로, 마이그레이션을 삭제해준다.
 - 이때, 유의할점은 **__init__.py**는 **절대 삭제하지 않는다**.
  ~~~
  #MAC OS 경우
  find . -path "*/migrations/*.py" -not -name "__init__.py" -delete
  ~~~
   