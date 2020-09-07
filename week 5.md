# EUID_UISD

# 1day

## 웹접근성과 웹표준

### 웹접근성(Web Accessibility)이란?
  * 웹사이트에서 제공하는 정보를 **차별 및 제한없이 동등**하게 이용할 수 있도록 보장하는 것. 즉, 신체적 조건이나 환경적 조건에 관계없이 웹에 접근해서 정보를 이용할 수 있도록 하는 것.
    + 장애인 및 고령자를 포함한 모든 사람
        다양한 platform 및 Device와 웹브라우저 등 모든 환경 

### 웹접근성 향상을 위한 방법
  * 비장애인은 이용할 수 있지만 장애인은 이용할 수 없다면 추가적으로 장애인을 위한 별도의 서비스를 제공해주면 된다. 또한 서로 다른 환경에서도 이용할 수 있도록 환경에 적합한 서비스를 별도로 제공해주면 된다. 
  
#### 웹 접근성 지침
  * WAI에서 권하고 있는 웹접근성 지침(WCAG)을 준수한다.
    + 인식
    + 운용
    + 이해
    + 견고


#### 웹표준 기술
  * 웹에서 표준적으로 사용되는 기술이나 규칙
  * 웹서비스를 제작할 때 웹표준 기술을 활용한다.
    + HTML : 콘텐츠의 구조를 설계하고 의미를 부여하는 기술
    + CSS : 콘텐츠의 배치 및 스타일을 위한 기술
    + Javascript : 콘텐츠의 기슬을 구현하는 기술
    + WAI-ARIA : RIA를 위한 웹접근성 관련기술
      - 기존 HTML의 부족한 부분을 보완하여 웹접근성을 준수할 수 있도록 하는 기술  
      - WAI-ARIA 사례집 참고

### 웹접근성을 고려한 HTML 마크업

#### 기본 언어 설정 및 적절한 제목 제공
  * 웹접근성 지침(WCAG)의 원칙3 이해의 용이성, 원칙2 운용의 용이성을 참고
    + 콘텐츠는 이해할 수 있도록 제공 : (기본 언어 표시)주로 사용하는 언어로 명시
    + UI 구성요소는 조작 가능하고 내비게이션 할 수 있어야 한다. : (제목 제공) 페이지, 프레임, 콘텐츠 블록에는 적절한 제목을 제공해야함 
```html
<!DOCTYPE html>
<html lang="ko-KR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <!-- 해당 페이지의 내용을 알 수 있는 핵심키워드로 제공 
    주의! 모든 페이지의 타이틀이 같지 않고 각 페이지의 고유의 정보를 제공 
    불필요한 특수문자는 제공하지 않는다. -->
    <title>이디야 커피</title> 
</head>
</html>
```

#### 콘텐츠 구조(HTML5) 
```html
<body>
    <header>헤더</header>
    <main>메인</main>
    <footer>푸터 (숨김 콘텐츠)</footer>
</body>
```

#### 콘텐츠 구조 (WAI-ARIA)
  * 의미가 없는 div요소를 제공했다면 WAI-ARIA의 Landmark Role을 사용할 수 있다. 
  * 권장하는 방법은 아니다. 또한 HTML의 네이티브 요소와 혼용하여 사용하지 않도록 해야 한다. 
```html
<body>
    <div role="banner"> 헤더 </div>
    <div role="main""> 메인 </div>
    <div role="contentinfo"> 푸터 (숨김 콘텐츠) </div>
</body>
```

### 콘텐츠 제목 및 논리적인 순서

#### 논리적인 순서 
  * 웹접근성 지침(WCAG)의 원칙3 이해의 용이성 참고
    + (콘텐츠의 선형화) 프레임, 콘텐츠는 논리적인 순서로 제공해야 한다. 
  * 합리적인 마크업 순서. 메뉴 닫기 버튼을 마지막에 마크업하여 보조기기 사용자를 고려해야 함
    1) 메인 메뉴 열기 버튼 
    2) 메뉴 목록
    3) 메뉴 닫기 버튼

#### 콘텐츠 제목
  * 웹접근성 지침(WCAG)의 원칙2 운용의 용이성 참고
  * 메인 메뉴 영역과 음료정보 영역에는 디자인상 제목으로 간주될 수 있는 정보가 없다. 
  디자인적 관점에서 제목정보가 제공되고 있지 않더라도 독립된 콘텐츠 영역이라면 각각의 영역을 대표할 수 있는 콘텐츠 블록에 제목을 제공하여야 한다. 바로 숨김제목의 형태로 

#### SEO와 보조 기기를 위한 제목 제공
  * 콘텐츠 블록에 제목을 제공할 경우 주의할 점
    + 제목의 **계층 구조를 건너뛰지 않도록 주의**해야 한다. 
    + 예) h1요소 없이 h3요소를 사용하거나 h2 요소 다음에 h4요소를 사용하지 않도록 해야 한다. 

```html
<body>
    <header>
        <h1>EDIYA DOFFEE</h1>
        <h2 class="a11y-hidden">메인 메뉴</h2> <!--숨김 콘텐츠--> 
    </header>
    <main>
        <h2 class="a11y-hidden">이디야 음료</h2>  <!--숨김 콘텐츠-->
    </main>
    <footer>  푸터 (숨김컨텐츠) </footer>
</body>
```

```html
<body>
    <header>
        <h1>EDIYA DOFFEE</h1>
<!-- 메뉴열기 : 배경이미지로 제공하기 때문에 보조기기 사용자는 버튼의 용도를 이해할 수 없다. 이때 WAI-ARIA를 사용한다. -->
        <button>
            <span class="ir"></span>
        </button> 
        <nav>
            <h2 class="a11y-hidden">메인 메뉴</h2> <!--숨김 콘텐츠-->
            <ul>
                <li><a href="#">메뉴</a></li>
                <li><a href="#">이디야멤버스</a></li>
                <li><a href="#">이디야커피랩</a></li>
                <li><a href="#">이디야컬쳐랩</a></li>
                <li><a href="#">공지사항</a></li>
                <li><a href="#">매장찾기</a></li>
            </ul>
            <button><span>X</span></button> 
            <!-- 메뉴닫기 : X버튼 또는 곱하기 버튼으로 인식할 수 있다. -->        
        </nav>
    </header>
</body>

<!-- WAI-ARIA 사용 -->
<body>
    <header>
        <h1>EDIYA DOFFEE</h1>
        <button type="button" class="button is-open-menu"
                title="메뉴 열기" aria-label="메뉴 열기"></button>
            <span class="ir"></span>
        </button> 
        <nav hidden class="app-navigation">
            <h2 class="a11y-hidden">메인 메뉴</h2> <!--숨김 콘텐츠-->
            <ul class="reset-list">
                <li><a href="#">메뉴</a></li>
                <li><a href="#">이디야멤버스</a></li>
                <li><a href="#">이디야커피랩</a></li>
                <li><a href="#">이디야컬쳐랩</a></li>
                <li><a href="#">공지사항</a></li>
                <li><a href="#">매장찾기</a></li>
            </ul>
            <button type="button" class="button is-close-menu"
                    title="메뉴 닫기" aria-label="메뉴 닫기">
                <span class="close" aria-hidden="true">X</span> <!-- aria-hidden="true" 해당 영역의 정보 무시 -->
            </button>  
        </nav>
    </header>
</body>
```