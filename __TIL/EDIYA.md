# EUID_UISD

## 이디야 예제
  
# 여러가지 정리 

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
  * 정답은 없다, 상황과 환경에 따라 마크업하면 된다. 
  * 예시 - 마크업의 여러가지 방법
```html
<!-- 1 -->
<!-- section 태그를 형제요소로 마크업하는 방법 -->
<section>
  <h1></h1>
  <p></p>
</section>
<section>
  <h1></h1>
  <p></p>
</section>

<!-- 2 -->
<!-- section 태그를 자식요소로 마크업하는 방법 -->
<section>
  <h1></h1>
  <p></p>
    <section>
      <h2></h2>
      <!-- h1요소가 section의 자식으로 들어가면서 h2요소가 됨 -->
      <p></p>
    </section>
</section>
```
### 논리적인 순서 (웹접근성)
  * 기본적으로 코드를 입력할 때 위에서 아래로, 왼쪽에서 오른쪽으로 입력한다고 생각하지만 무조건적으로 옳은 방법은 아니다.
  * 접근성을 고려해서 보조기기가 마크업 순서대로 화면을 읽어준다는 것까지 고민해야 한다.
  * 예를 들어, 내비게이션 목록을 열었을 때 메뉴 닫기 버튼이 맨 위에 마크업되어 사용자에게 처음부터 읽어주는 것보다 맨 마지막에 마크업하여 사용자에게 목록의 내용을 읽어준다음 메뉴 닫기 버튼을 읽어주는 것이 더 바람직하다. 


### class를 입력할 때
  * class를 사용해서 태그의 이름을 작성할 때 
    - 명시적으로 작성하는 것이 좋다. 
    - 위치에 관련된 이름은 사용 X
    - 코드 표기법을 참고하기!
  * 웹 접근성관련 클래스 `a11y-hidden` 
    + 화면에 렌더링 되는 텍스트는 아니지만 보조기기가 화면을 읽을 때 해당 컨텐츠를 읽도록 하기 위한 것이다.
    + 제목이 없는 페이지에서는 이렇게 명시해주시만 제목이 있는 페이지에서는 굳이 사용할 필요는 없다. 
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

## IR 기법 (웹표준)
  * 이미지 대체텍스트 제공을 위한 CSS 기법이다. 
  * 다양한 CSS 기법을 사용하여 이미지 대체텍스트를 제공할 수가 있다.
  * 참고 : <http://darum.daum.net/convention/css/css_ir>
    + 들어가서 Phark Method 방법도 한 번 보기

### IR 기법 - WA IR (권장)
  * 이미지로 대체할 엘리먼트에 배경이미지를 설정하고 글자는 span 태그로 감싼 후 z-index:-1을 이용하여 화면에 안보이게 처리한다. 
  * 예시
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

## 크로스 브라우징

----

# 이디야 예제 구조 정리

## 헤더바 

## 내비게이션

## 음료 목록

## 로그인 폼

### 로그인 페이지 본문 마크업
```html
<!-- 1 -->
<!-- 제목과 본문을 한 덩어리로 묶기 위해 div 태그를 사용했다. -->
<div class="login-page-title">
    <h2>로그인</h2>
    <p>
      <span lang="en">Welcome, Ediya Coffee</span>
    이디야커피에 오신 것을 환영합니다.
    </p>
</div>

<!-- 2 -->
<!-- 제목과 본문을 같이 그룹핑하지 않았지만 본문은 같은 이름의 class를 사용했다.  -->
<h2 class="member-headline">로그인</h2>
<p class="member-information" lang="en">Welcome, Ediya Coffee</p>
<p class="member-information">이디야커피에 오신 것을 환영합니다.</p>
```

