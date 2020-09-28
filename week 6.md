# EUID_UISD

## 오프라인 강의
  
## 구조
  * HTML의 기본적인 구조
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="./css/style.css">
  <title></title>
</head>
<body>
  <header>
    <nav></nav>
  </header>
  <main></main>
  <footer></footer>
</body>
</html>
```

### 구조화를 하기 전 고민하기
  * 코드를 직접 입력하기 전에 코드의 구조를 먼저 고민해보는 것이 더 중요하다. 
  * 정답은 없다, 여러가지 경우의 수를 고민해보고 적용해보자!
  * 예시 (`<section>` 태그를 사용할 때도 두 개를 따로 사용하는 방법, 태그 안에 태그를 또 넣어 자식요소로로 사용하는 방법이 있다.)
```html
<!-- 1 -->
<section>
  <h1></h1>
  <p></p>
</section>
<section>
  <h1></h1>
  <p></p>
</section>

<!-- 2 -->
<section>
  <h1></h1>
  <p></p>
    <section>
      <h2></h2>
      <p></p>
    </section>
</section>
```
### 논리적인 순서 
  * 기본적으로 코드를 입력할 때 위에서 아래로, 왼쪽에서 오른쪽으로 입력한다고 생각하지만 무조건적으로 옳은 방법은 아니다.
  * 접근성을 고려해서 보조기기가 마크업 순서대로 화면을 읽어준다는 것까지 고민해야 한다.
  * 예를 들어 


### class를 입력할 때
  * class를 사용해서 태그의 이름을 작성할 때 
    - 명시적으로 작성하는 것이 좋다. 
    - 위치에 관련된 이름은 사용 X
  * 웹 접근성관련 클래스 `a11y-hidden` 
    + 화면에 렌더링 되는 텍스트는 아니지만 보조기기가 화면을 읽을 때 해당 컨텐츠를 읽도록 하기 위한 것이다.
    ```html
    <h2 class="a11y-hidden">메인 메뉴</h2> <!--숨김 콘텐츠--> 
    ```
  
## 코드 표기법
  * 가장 중요한 것은 **일관성**을 유지하며 사용하는 것이다.
  * 상황에 맞게 사용한다. 

  * 낙타 표기법 (Camel Case)
    + 낙타 표기법이라고도 함
    + 띄어쓰기가 있는 부분의 문자를 대문자로 표기한다. 
    + 예) app Header
  
  * 파스칼 표기법 (Pascal Case)
    + 쌍봉낙타 표기법이라고도 함.
    + 낙타 표기법에서 맨 앞의 문자끼리 대문자로 표기한다. 
    + 예) App Header

  * 스네이크 표기법 (Snake Case)
    + 띄어쓰기 대신 언더바(_)로 표기한다.
    + 예) app_header

  * 케밥 표기법 (Kebab Case)
    + 띄어쓰기 대신 하이픈(-)으로 표기한다. 
    + 예) app-header

## `<ir>`은 이미지? 
  - 참고 : <https://m.blog.naver.com/PostView.nhn?blogId=tcloe8&logNo=221600050263&proxyReferer=https:%2F%2Fwww.google.com%2F>
```html
<button type="button" class="button is-open-menu" aria-label="메뉴 열기" title="메뉴 열기">
  <span class="ir"></span>
</button>
```  
```css
.is-open-menu .ir {
    display: block;
    width: 26px;
    height: 22px;
    background-color: orange;
    background-image: url(../images/navigation-button.gif);
}
```

## IR 기법 (웹표준)
  * 이미지 대체텍스트 제공을 위한 CSS 기법이다. 
  * 다양한 CSS 기법을 사용하여 이미지 대체텍스트를 제공할 수가 있다.
  * 참고 : <http://darum.daum.net/convention/css/css_ir>
    + 들어가서 Phark Method 방법도 한 번 보기

### WA IR (권장)
  * 이미지로 대체할 엘리먼트에 배경이미지를 설정하고 글자는 span 태그로 감싼 후 z-index:-1을 이용하여 화면에 안보이게 처리한다. 

```html
<button> 
    <span>검색</span> 
</button> 

<a href="#"> 
    <span>검색</span> 
</a>
```
```html
<button type="button" class="button is-open-menu" aria-label="메뉴 열기" title="메뉴 열기">
  <span class="ir"></span>
</button>
```  
```css
.is-open-menu .ir {
    display: block;
    width: 26px;
    height: 22px;
    background-color: orange;
    background-image: url(../images/navigation-button.gif);
}
```

### 크로스 브라우징
  
#### 웹 표준의 준수

## 온라인 밋업 수업

### 여성 메거진 레이아웃 예제

* CSS reset vs normalize
  + reset 
    
  + normalize 
    - 브라우저를 최소화로 일반화 한것 
    - 링크를 복사해서 사용하는 이유? 
      본인이 직접 기본값을 입력해서 사용할 수 있지만 여러가지 운영체제를 고려해서 작성해야 하기 때문에 번거롭다. 그래서 만들어진 것(?)을 사용한다. 
  + CSS에서 `@import`를 사용해서 불러오는 것 보다 html의 `<link>`요소를 사용하여 불러오는 것을 권장
    - css에서 링크를 불러오게 되면 네트워크의 속도가 느려진다. 
  + 예시
```html
<link rel="stylesheet" href="css/main.css">

<!-- 또는 -->
<link rel="stylesheet" href="css/normalize.css">
```
```css
@import url(https://cdnjs.cloudflare.com/ajax/libs/normalize/8.0.1/normalize.min.css);
```





* 레이아웃 순서 
  1. 스타일 시크 불러오기
  2. normalize 불러오기
  3. 배경색 
  4. `<h2>`에 `class`를 주고 text입력
  5. 폰트 스타일링하기 
    + 폰트 속기형!
    + Web font
  6. `<h2>`에서 position을 사용해서 위치 이동하기
    + margin 확인하기 
  7. 배경 이미지 불러오기 (신발)
    + 여기서 벡터/ 비트 이미지 구분 하기
    + .jpg/ .png의 차이점  
    + 픽셀농도
    + min-height: 100vh;

