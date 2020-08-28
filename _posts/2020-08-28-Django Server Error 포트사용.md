---
title: "Git 버전관리 기본개념 이해하기"
categories:
  - Django
  - 웹개발
tags:
  - 웹개발
  - Web
  - port
  - 8000
  - 포트
  - 맥북
  - OSX
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---

## 포트관련 오류
  - Django 서버 재실행 시 발생될 수 있는 오류
   * Error: That port is already in use

 ### 해결책 : sudo lsof -tf -i tcp:8000 | xargs kill -9   
   