---
title: "Django UUID를 통한 파일명 정하기 "
categories:
  - 웹개발
  - Django
tags:
  - 웹개발
  - Python
  - Django
  - uuid
  - file name
  - 파일명
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## UUID를 통한 파일명 정하기 소스코드 
~~~
import os
from uuid import uuid4
from django.utils import timezone

def uuid_name_upload_to(instance, filename):
  app_label = instance.__class__._meta.app_label   # 앱 단위로 설정
  cls_name = instance.__class__.__name__.lower()   # 모델 단위로
  ymd_path = timezone.now().strftime('%Y/%m/%d')   # 업로드하는 년/월/일 단위
  uuid_name = uuid4().hex  # 하이픈 없앤 uuid 32글자
  extension = os.path.splitext(filename)[-1].lower()  # split을 하면, 파일명과 확장자 튜플로 반환 
  return '/'.join([
    app_label,
    cls_name,
    ymd_path,
    uuid_name[:2],  # uuid 첫 두글자만 추출
    uuid_name + extension,
  ])


~~~