---
title: "파이썬 for문 range"
categories:
  - 파이썬
  - 머신러닝
tags:
  - Python
  - machine learning
  - for
  - 반복문
  - range
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## for문에서 함께 사용되는 range 함수
range함수는 숫자 리스트를 자동으로 만들어주는 함수
~~~
a = range(10)
a
range(0,10)  # ← 0,1,2,3,4,5,6,7,8,9
~~~

헤깔리지 말자. 0은 포함하고 10은 포함하지 않는다.  
**range**  
  range(2,5)
  2 ≤ x < 5
{: .notice--info}


**List 슬라이싱**  
  리스트에서 슬라이싱을 수행하면
  a[2:5]
  a[2] ≤ x < a[5]
{: .notice--info}
