# Background-Image-Scroll-Effect
<img src="./image.gif" width="500px">

## 효과  
스크롤을 내리면 배경이 흐려지면서, 텍스트가 자연스럽게 나오는 효과  

## 이미지 가져오기  
- unsplash  
https://unsplash.com/ko

## 학습
### 1. JS : Window.pageYOffset (Window.scrollY)
- 문서가 수직으로 얼마나 스크롤됐는지 픽셀 단위로 반환   
  
- Window.scrollY 와 동일 
  
- 읽기 전용 속성   
  ```
  // 콘텐츠를 100픽셀씩 스크롤하고 pageXOffset 및 pageYOffset에 경고

  window.scrollBy(100, 100);
  alert(window.pageXOffset + window.pageYOffset);
  ```
- 브라우저간 호환성을 위해서는 window.scrollY 대신 window.pageYOffset을 사용 
  
- Internet Explorer 9 미만의 구형 환경에서는 두 속성 모두 지원하지 않으므로 또 다른 비표준 속성을 사용해야 합니다. 다음은 완벽히 호환되는 코드의 예시

  ```
  var supportPageOffset = window.pageXOffset !== undefined;
  var isCSS1Compat = (document.compatMode || "") === "CSS1Compat";

  var x = supportPageOffset
    ? window.pageXOffset
    : isCSS1Compat
      ? document.documentElement.scrollLeft
      : document.body.scrollLeft;
  var y = supportPageOffset
    ? window.pageYOffset
    : isCSS1Compat
      ? document.documentElement.scrollTop
      : document.body.scrollTop;

  ```

### 2. JS : Window.pageXOffset (Window.scrollX) 
- 문서가 수평으로 얼마나 스크롤됐는지 픽셀 단위로 반환     
  
- Window.scrollX 와 동일 
  
- 읽기 전용 속성   
  ```
  // 문서의 현재 스크롤 위치가 400픽셀이 넘으면 맨 처음으로 돌아갑니다.
  if (window.scrollX > 400) {
    window.scroll(0, 0);
  }
  ```

- nternet Explorer 9 미만의 구형 환경에서는 두 속성 모두 지원하지 않으므로 또 다른 비표준 속성을 사용해야 합니다. 다음은 완벽히 호환되는 코드의 예시 
  ```
  var supportPageOffset = window.pageXOffset !== undefined;
  var isCSS1Compat = (document.compatMode || "") === "CSS1Compat";

  var x = supportPageOffset
    ? window.pageXOffset
    : isCSS1Compat
      ? document.documentElement.scrollLeft
      : document.body.scrollLeft;
  var y = supportPageOffset
    ? window.pageYOffset
    : isCSS1Compat
      ? document.documentElement.scrollTop
      : document.body.scrollTop;

  ```

## 학습 출처 
- 유튜브  
https://www.youtube.com/@JavaScriptKing     

- JS  
https://www.w3schools.com/jsref/prop_win_pageyoffset.asp    
https://developer.mozilla.org/ko/docs/Web/API/Window/scrollY  
https://www.w3schools.com/jsref/prop_win_screenX.asp   
https://developer.mozilla.org/ko/docs/Web/API/Window/scrollX   

- 키워드     
Window.pageYOffset (Window.scrollY)   
Window.pageXOffset (Window.scrollX)    