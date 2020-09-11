---
title: "Django API with Class Based Views"
categories:
  - Django
  - 웹개발
tags:
  - API
  - RESTful
  - REST
  - REST API
  - Django
  - web
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## Class Based View 방식으로 API 만들기

전에 배웠던, API functionality [API with View Function](https://gymnopedies7.github.io/django/%EC%9B%B9%EA%B0%9C%EB%B0%9C/Django-API-Function-View/) 과 동일한 결과값을 보이지만, class based view방식으로 만들어보자.

Class based view 방식은 Django 에서 추천하는 방식이므로, 향후 모든 API는 Class Based View 방식으로 할 예정이다.  
장고에서 추천하는 이유는, 여러 이점이 많기 때문인데 그중에서도 다른 클래스로부터 특성을 상속할수 있는 등 유연하기 때문이다.

~~~
from rest_framework import status
from rest_framework.views import APIView
from rest_framework.response import Response

# Create your views here.
class Add_Values(APIView):
  def post(self, request, format=None):
    sum = 0
    data = request.data
    for key in data:
      sum += data[key]
    response_dict = {'sum' : sum}
    return Response(response_dict, status=status.HTTP_201_CREATED)
~~~

url에는 아래와 같이 추가하면 된다.
~~~
url patterns = [
  path('add_values/', views.Add_Values.as_view(), name= 'api_add_values'),
]
~~~

