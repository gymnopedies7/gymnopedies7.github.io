---
title: "JavaScript Tutorial : 이벤트 Event "
categories:
  - 웹개발
  - Javascript
tags:
  - 웹개발
  - JS
  - JavaScript
  - 자바스크립트
thumbnail: /assets/image/github.jpg
toc: True
toc_sticky: True
---


## Event 란?
 - 이벤트는 Web상에서 일어나는 일을 인식해서, 이후 동작처리를 하기위한 기본적인 장치
 - HTML은 정적. 쉽게말해 사용자랑 소통을 할 수 없고 그냥 코딩해놓은 그대로만 보여주는 반면
 - JS는 동적. 사용자가 한 행위(Event)에 대해서 적절히 반응을 해줄 수 있다.

### onclick : 클릭 시 일어날 수 있는 이벤트
~~~
<input type = "button" value="hi" onclick="alert('hi')">
~~~

### onchange : 무언가 바뀌었을 때 이벤트
~~~
<input type="text" onchange="alert('changed')">
~~~

### onkeydown : 키를 눌렀을 때 이벤트
~~~
<input type="text" onkeydown="alert('keydown!')">
~~~

## 검색방법
 - javascript ~~~ event attribute