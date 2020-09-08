---
title: "Django API Function View"
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


## View Function으로 API 만들기

전제조건은 url을 구성하여 Request를 받는것.

이후, Django에서 View Function을 구현하기 위해서는 Fucntion 선언 앞에 Decorator를 붙여야 한다.  
'@api_view' 이 decorator는 파이썬 function을 API Function으로 전환해준다.   
또한, 어떤 종류의 request가 만들어질지 말해줘야 한다. 아래 예시를 보자.

~~~
from rest_framework import status
from rest_framework.decorators import api_view
from rest_framework.response import Response

# Create your views here.
@api_view(['GET', 'POST'])
def api_add(request):
    sum = 0
    response_dict = {}
    if request.method == 'GET':
        # Do nothing
        pass
    elif request.method == 'POST':
        # Add the numbers
        data = request.data
        for key in data:
            sum += data[key]
        response_dict = {"sum": sum}
    return Response(response_dict, status=status.HTTP_201_CREATED)
~~~



