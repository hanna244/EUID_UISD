# EUID_UISD

# 1day

## HTML - [HTML 이란?]
  * 확장자 : `<.html>`
  * HTML(HyperText Markup Language)
  * **구조를 설계할 때 사용되는 언어**이며 하이퍼링크 시스템을 가지고 있다.   
  * HTML은 콘텐츠의 의미를 설명하는데 유일한 목적을 가집니다.
  * 비주얼 디자인(모양, 색, 크기 등)이 목표가 아니라, 구조 설계(Structure Design)를 목표로 합니다. 

 H : Hyper text – 하이퍼링크   
 T : Text - 언어   
 M : markup – 구조   
 L : 랭귀지 - 언어

---
## HTML - 시멘틱 마크업(Semantic Markup)
  * 컨텐츠를 브라우저가 해석을 하면서 자동으로 여러가지의 **HTML 요소를 구성 하는 일**을 마크업이라고 한다.
  * 넌시멘틱 마크업(Non-Sementic Markup) : 의미가 없는 구조
    + Ex) `<div>`
  * 브라우저는 파일 확장자에 따라서 임의의 형태로 해석한다. 
  * 구조를 의미있게 구성하기 위해서는 공부할 때 각 태크 또는 요소 마다의 의미를 정확하게 알고 적용할 필요가 있다.
  * 제목 : `<h>` : heading (1-6 레벨이 있음)
  * 단락 : `<p>` : paragraph
<h2>1. HTML 이란?</h2>

<ul>
  <li>H : Hyper text – 하이퍼링크</li>
  <li>T : Text - 언어</li>
  <li>M : markup – 구조</li>
  <li>L : 랭귀지 - 언어</li>
</ul>

<h2>2. 시멘틱 마크업 (Semantic Markup)</h2>
 <ul>
  <li>컨텐츠를 브라우저가 해석을 하면서 자동으로 여러가지의 HTML 요소를 구성 하는 일을 마크업이라고 한다.</li>
  <li>언시멘틱 마크업 : 의미가 없는 구조</li>
  <li>구조를 의미있게 구성하기 위해서는 공부할 때 각 태크 또는 요소 마다의 의미를 정확하게 알고 정욕할 필요가 있다.</li>
  <li>제목 : heading → h1</li>
  <li>단락 : paragraph→ p</li>
 </ul>


<h2>3. HTML 문서를 작성하는 기본 문법</h2>
 <ul>
  <li>웹 페이지는 헤드(head) 영역과 바디(body) 영역으로 구성된다.</li>
  <li>문서 타이틀(title)은 웹 페이지의 제목으로 브라우저 탭에 표시된다.</li>
 </ul>
 
---
## HTML - 기본 문법
 
  * 웹 페이지는 **헤드(head)** 영역과 **바디(body)** 영역으로 구성
  문서 타이틀(title)은 웹 페이지의 제목으로 브라우저 탭에 표시된다.
  * 브라우저는 정해진 규칙에 따라 제작자가 문서를 작성해주면 그 내용을 해석해서 사용자가 보는 화면(UI)에 그것을 처리해 주는 역할을 한다.

### 기본문법
  ```html
  <여는 태그> 컨텐츠 /<닫는 태그>
  <태그이름 속성="값"> 컨텐츠 </태그이름>
  ```
  *
    + 여는 태그와 닫는 태그의 이름은 같아야 한다.
    + 컨텐츠(element content) : 사용자에게 보여지는 중요한 내용

### HTML 용어 
  ```
  element : 요소
  open tag : 여는 태그
  tag : 닫는 태그
  attribute : 속성
  value : 값
  ```

### 브라우저 기본 구조
  ```html
  <html>
  <head></head> (2)
  <body>
  <p title="Delopment Tools">개발 도구(DevTools)</p> (1)
  </body>
  </html>
  ```
  *
    + (1) (내용 컨텐츠 추가, 단락으로 의미 구조화, title이라는 속성을 부여해서  값으로는 Delopment Tools이라는 것을 명시)
    + (2) 사용자가 보는 브라우저 탭 (타이틀, 문서의 제목)

### 브라우저 인코딩
  * 확인 방법
    + Devtools - Console - 입력 (document.characterSet)
  * 인코딩 설정
    ```html
    <meta charset="utf-8">
    ```

## HTML - 텅 빈 요소(Empty Element) (콘텐츠를 감싸지 않는 요소)
  * 
    + 닫는 태그가 없다, 내용이 비어있다는 의미
    + 여는 태그 만으로서 정보를 제공할 수 있는 요소이다
    + 내용 컨텐츠를 감싸지 않았기 때문이다 (내용 x)
    + `<meta>` 등

## 들여쓰기(Indentation)
  * HTML 요소 간 관계(부모, 자식, 형제)를 구분하기 용이 함에 들여쓰나, 브라우저는 코드가 한 줄 이어도 해석하는데 아무런 문제가 없습니다.
  * 이를 통해 계층 구조를 시각적을 표현한다.

### HTML 요소 간 관계
  ```HTML 
  <html> : root element 모든 요소의 조상
    <head>
      <meta> : head요소의 자식
      <title></title> : head요소의 자식
    </head> : html의 첫 번째 자식 first child
    <body>
      <p></p> : body요소의 자식
    </body> : html의 마지막 자식 last child
  </html>
  ```
  * `<html>`,`<head>`,`<body>`요소 사이에는 어떠한 것도 들어 올 수 없다.
  * `<head>`,`<body>`요소는 각각 다른 성질의 자식들을 가질 수 있다

### DOCTYPE (Document Type Definition)
  * 표준모드와 비표준모드를 설정 
  * 웹 표준 문서이자, 모든 웹브라우저에서 호환되는 문서가 된다.(표준모드)
  * 만약 DOCTYPE 코드가 없다면 해당 문서는 비표준 문서가 된다.
  * 페이지의 가장 상위에 존재해야 한다.
  * 소문자, 대문자 구분 X
  * 대부분의 웹브라우저에서 표준모드를 사용하기 때문에 DOCTYPE을 사용해서 페이지를 작성하는 것이 좋다.


<h2>5. 표준 호환모드</h2> 
 <ul>  
  <li>HTML 요소 간 관계(부모, 자식, 형제)가 있다.</li>
  <li>HTML element 는 root element로 모든 요소의 조상이 될 수 있다.</li>
  <li>HTML element
     <ul>
        <li>head : first child</li>
        <li>body : last child</li>
     </ul>
  </li>
  <li>각 요소 사이에는 어떠한 것도 들어 올 수 없다.</li>
</ul>

<h3>DOCTYPE (document. Doctype)</h3>
 <ul>
    <li>표준모드와 비표준모드를 설정</li>
    <li>웹 표준 문서이자, 모든 문서에서 호환되는 문서가 된다.(표준모드)</li>
    <li>만약 DOCTYPE 없다면 해당 문서는 비표준 문서가 된다.</li>
    <li>페이지의 가장 상위에 존재해야 한다.</li>
    <li>소문자, 대문자 구분 x</li>
    <li>대부분의 웹브라우저에서 표준모드를 사용하기 때문에 DOCTYPE을 사용해서 페이지를 작성하는 것이 좋다.</li>
</ul>

<h2>6. 문서에 사용되는 주 언어 설정</h2>
```html
<html lang=”ko-KR”>
```
<h2>7. 제목과 단락</h2>

<h3>단락(Paragraph)</h3>
 <ul>
   <li>사용자가 가장 많이 읽는 콘텐츠는 단락(Paragraph)입니다. 단락은 p 요소로 구성됩니다.</li>
   <li>글의 덩어리를 나눌 때 단락을 사용함</li>
</ul>


<h3>제목(Headings)의 단계</h3>
 <ul>
  <>제목 레벨 : 1 ~ 6단계
    <ul>
      <li>1단계는 문서에서 하나만 작성 </li>
      <li>2단계부터는 여러 개의 제목을 사용할 수 있다.</li>
    </ul>
  

<h3>주석(Comments)</h3>
 <ul>
   <li>HTML 주석은 브라우저에서 해석되지 않습니다.</li>
</ul>

 
## HTML 이미지 & 피규어 & 캡션


* 웹 문서에 주로 사용되는 이미지 포멧
  + 비트맵 그래픽 파일 : JPG, GIF, PNG 포멧이 사용
  + 벡터 그래픽 파일 : SVG 포멧이 사용

    - JPG 이미지
      + JPG 이미지는 압축률이 높고, 다양한 색상을 처리하도록 설계되었습니다. 사진 또는 복잡한 그래픽(그레디언트와 같은) 이미지에 많이 사용 되는 포멧 입니다. 하지만 GIF, PNG와 달리 투명한 픽셀을 허용하지 않습니다.
    - PNG 이미지
      + PNG는 사진이나 애니메이션을 제외한 모든 유형에 적합합니다. 사진의 경우 동일한 품질의 PNG 파일 크기가 일반적으로 JPG 보다 크기 때문입니다. 하지만 JPG와 달리 투명 처리가 가능해 아이콘, 로고, 다이어그램 등에 사용하면 좋습니다.
    - GIF 이미지
      + GIF는 표현 가능한 색상이 256색으로 제한되어 있기에 사진에는 적합하지 않습니다. 하지만 애니메이션을 적용할 수 있는 포멧으로 단순한 그래픽의 애니메이션에 사용하면 좋습니다. 투명하게 처리가 가능하긴 하지만, PNG 포멧 보다 표현력이 떨어집니다.
    - SVG 이미지
      + SVG는 벡터 기반 그래픽 포멧으로 품질 손실없이 확대, 축소 할 수 있습니다. 오늘날 처럼 다양한 스크린에 대응하는 반응형 웹 디자인에 매우 적합합니다. 왼쪽 이미지인 SVG와 달리 오른쪽 이미지인 비트맵 이미지는 크기를 키울 경우 뿌옇게 표시됩니다. (픽셀로 구성된 그래픽 이기 때문)

## 이미지 (images)
  * `<img>`
```html
<img src =”소스테이터” alt=”대체텍스트”>
```
  * souce : `<src>`
  * alternate test : `<alt>` (대체 텍스트)
    + alt 속성을 잘 설정해두면, 시각 장애인이 아니더라도 도움을 받을 수 있습니다. 이미지 링크가 깨질 경우, 화면에 alt 속성 값이 출력 되어 어떤 이미지 였는지 정보를 제공할 수 있습니다.

### HTML 문서는 이미지를 포함시키지 않는다</h3>
    + 한글이나 워드는 문서에 이미지를 포함시키지만 HTML 문서는 이미지를 포함시키지 않는다.
    + 이미지를 연결해서 사용한다.
    + HTML 파일에 이미지가 포함이 된다면 파일의 용량이 커지기 때문에 속도가 느려진다.
  
### CSS에 이미지를 연결한 경우 (의미있는 이미지)
  * 접근성과 관련있다.
    + 해당 이미지를 의미있는 이미지로 설정하기 위해 css에서 이미지를 연결한다. 
    + 예) 햄버거 버튼 이미지를 삽입할때 css에서 이미지 연결
  ```html
  <button type="button" class="button is-open-menu" aria-label="메뉴 열기" title="메뉴 열기">
    <span class="ir"></span>
  ```
  ```css
  .is-open-menu .ir {
    background-image: url(../images/navigation-button.gif);
  }
  ```

## 피규어(Figure)
  * `<figure>`
<ul>
  <li>도표, 차트, 이미지, 표를 감쌀 때 사용되는 요소</li>
  <li>**피규어 요소 안에 피그캡션 요소**를 넣어 줄 수 있다.</li>
</ul>


## 캡션 (Caption)
  * `<figcaption>`
<ul>
  <li>캡션은 이미지와 묶여서 하나의 덩어리가 되어야 한다.</li>
  <li>피규어(Figure)요소를 사용해서 이미지와 캡션 요소를 하나도 감쌀 수 있다.</li>
</ul>


<h3>피규어(Figure)</h3>
<ul>
  <li>도표, 차트, 이미지, 표를 감쌀 때 사용되는 요소</li>
  <li>피규어 요소 안에 피그캡션 요소를 넣어 줄 수 있다.</li>
</ul>

<h2>9. 문법 검사</h2>

<p>검사 사이트 (http://validator.w3.org/)
  엔티티 코드 (http://entitycode.com/)</p>


## HTML 목록 디자인
  * 목록(List)
    + 순차 (ordered) : `<ol>`
    + 비순차 (unordered) : `<ul>`
  * 목록 아이템 (List Item)
    + `li`은 `ul`, `ol` 안에 들어갈 수 있다.
  * 중첩해서 사용 가능하다. 
    + `<ul>`안에 `<ul>`이 또 들어갈 수 있다.
    + `<ul>`안에 `<ol>`이 들어갈 수 있다.
  * 예시
```html
<ul>
  <li></li>
  <li></li>
  <li></li>
</ul>

<!-- 중첩목록 -->
<ul>
  <li>item-1</li>
  <li>item-2
  <!-- </il> 태그를 여기에 입력하지 않음, 확인하기 -->
    <ul>
      <li>item-2-1</li>
      <li>item-2-2
        <ul>
          <li>item-2-2-1</li>
          <li>item-2-2-2</li>
        </ul>
      </li>
    </ul>
  <!-- </li> 태그입력 -->
  </li>
</ul>

<!-- 비순차 목록 안에 순차 목록 -->
<ul>
  <li>item-1</li>
  <li>item-2
    <ol>
      <li>item-2-1</li>
      <li>item-2-2</li>
    </ol>
  </li>
</ul>
```


---
# 2day

## 질문
 * Q) 문법이나 속성을 코드로 메모하는 방법을 모르겠습니다.</p>
 * Q) 예를들어 위의 방법을 궁금해서 MDN 사이트를 이용한다고 할 때
  어떤식으로 검색을 해야하는 지 모르겠습니다.
  '코드', '속성'등의 키워드로 검색을 해도 원하는 정보를 얻기가 쉽지가 않네요... 이용법을 검색해도 잘 안나오고요.. 

## 앵커와 하이퍼링크

### 앵커(anchor)
  * `href` 특성을 통해 다른 페이지나 같은 페이지의 어느 위치, 파일, 이메일 주소와 그 외 다른 URL로 연결할 수 있는 하이퍼링크를 만든다. 

  * 예시 
```html
<!-- 같은 페이지 내에서 이동 -->
<ul>
  <li><a href="#intro">소개</a></li>
</ul>

<h3 id="intro">소개</h3>
```

### 웹 문서에 URL을 입력하는 방법
  * 절대 경로
     + 현재 HTML 문서와 상관없이 URL 주소를 사용해 리소스를 찾는 것을 말한다. 
     + `<a href="http://domain.com/resource.html"></a>`
  * 상대 경로 
      + 현재 HTML 문서에서 상대적인 위치를 설정하는 것을 말한다. 
      + `<a href="../misc/extras.html"></a>`
  * 루트 경로 
    + 현재 HTML 문서가 존재하는 영역의 최상위 루트 경로에서 대상을 찾는 것을 말한다. 
    + `<a href="/images.html"></a>`

## 정의 목록

  * 설명목록(Description List) : dl (설명하는 것들을 묶어주는 그룹 역할)
  * 용어(Description Term) : dt (내부에 해당하는 용어)
  * 기술(Description Description) : dd (그 용어를 설명하는 역할)
  * **dt는 인라인 요소이며, dd는 블럭 요소입니다. 때문에 dt 안에 블럭 요소를 넣으면 안된다**
  * 정의형 목록에서는 `<dd>`값이 바뀔 수 있다면, 그것은 정의형이 될 수 없기 때문이다. 이미 정의가 되어 있거나 설명이 정해져 있는 경우에만 사용할 수 있는 태그이다.
  * `<dl><dt><dd>`는 1:1로 쌍을 이룰 때 사용하는 것을 권장한다.
    + 스크린리더는 `<dt>`와 `<dd>`를 1:1로 쌍을 이룰 때 사용하는 것이 가장 정확한 의미를 읽어내어 스크린리더 사용자의 이해가 쉬워진다. 반드시 정의형이나 설명형을 만족하지 않더라도 제목과 데이터가 1:1로 쌍을 이룰 때만 사용하는 것을 권장한다.
    + <dt>는 1개이고 <dd>가 2개 이상을 사용해도 문법 오류는 발생하지 않지만, <dl><dt><dd> 태그 사용이 적합한 구조인지 다시 한번 생각해 보는 것이 좋다. 
  * [참고] : <https://aoa.gitbook.io/skymimo/aoa-2019/tip/dl-dt-dd-.>

```html
<body>
<dl>
  <dt>용어의 제목</dt>
  <dd>용어의 설명</dd>
</dl>
</body>
<!----------------->
<di> 
 // _
 <dt></dt>
 <dd></dd>
 // -

 <dt></dt>
 <dt></dt>
 <dd></dd>
 // -

 <dt></dt>
 <dd></dd>
 <dd></dd>
 </di>
```
 
<h2>3.인용과 줄 바꿈</h2>

<ul>
 <li>텍스트가 짧은 인라인 인용문 : q</li>
 <li>긴 인용문 : blockquote</li>
 <li>줄 바꿈(Line Break) : br</li>
  <lu>
  <li>절대 두 번 같이 사용할 수 없음</li>
  </lu>
 <li>출처(Citation) : cite</li>
</ul>

<h2>4.어휘 요소들</h2>

 <p>어휘 요소 활용 : strong, em, d, i</p>

 <h3>강조(의미가 있는 요소) : Semantic Elements - 강조의 의미를 부여하는 용도</h3>
  <ol>
  <li><h4>strong</h4></li>
   <p>내용의 중요성, 심각성, 긴급성을 강조할 경우 사용</p>
     <ul>
      <li>[중요성] : 제목/캡션의 글자 중 일부를 더욱 강조하는데 사용</li>
      <li>[심각성] : 경고 또는 주의를 주고자 할 때 사용</li>
      <li>[긴급성] : 문서의 다른 부분보다 빨리 보아야 하는 내용을 나타내는데 사용</li>
     </ul>
    
  <li><h4>em</h4></li>
   <p> : 특정 내용의 스트레스 강조 - 문장 의미를 변경</p>
    

 <h3>표현(의미가 없는 요소) : Non Semantic Elements - 다른 글자와 구분하기 위한 용도</h3>
  <li><h4>b</h4></li>
   <p> : 단순히 다른 글자와 구분된 용도로 사용. <br> 문서 요약의 주요 단어, 리뷰 제품 이름 등</p>
    <ul>
     <li>아래 조건에 부합하지 않을 경우 최종적으로 b 요소 사용을 고려</li>
      <ul>
       <li>제목은 h1 ~ h6 요소를 사용하고</li>
       <li>강조는 em 요소를 사용해야 하며</li>
       <li>중요도는 strong 요소로 표시 되어야 하고</li>
       <li>표시 또는 강조 표시된 텍스트는 mark 요소를 사용</li>
     </ul>
    </ul>
 
  <li><h4>i</h4></li>
   <p>다른 글자와 구분된 용도로 사용. <br> 기술적 용어, 다른 언어(목소리), 인물의 생각 등을 표현</p>
</ol>

<h2>[Figma]</h2>
<p>
UI 디자인에 필요한 그래픽 디자인 툴이다. <br> 
개발자와 디자이너가 실시간으로 같이 편집할 수 있는 기능이 있어
서로 효율적으로 작업 진행이 가능하다. <br> 
Window와 Mac 상관없이 UI 편집이 가능하다
</p>

---
# 3day

## CSS - [CSS란?] (Cascading Style Sheets)
  - CSS 언어는 HTML 문서인 Sheets를 스타일링 하는 역할을 하는데 일종의 규칙을 가지고 있는 스타일 언어이다.  

  * [참고]
    + CSS Current Work(CSS 스펙 등 CSS의 최신 기술등 ) : https://www.w3.org/Style/CSS/current-work  
 
## CSS - [CSS 기본 문법] 

  ```css
    선택자(대상) {        /* 대상 선택자, { 선언구간 시작 */
        속성1: 값;    /* ; 선언문 구분 */
        속성2: 값2;   /* : 속성, 값 구분 */
    }               /* 선언구간 종료 */
  ```
  ```css
  <html>
      <head>
          <style type="text/css"> /* MIME type 지정, 하지만 html 5 에서는 생략 가능 */
            h1 {
                color: deeppink;
                font-size: 2em;
            }
          </style>
      </head>
      <body>
          <h1>Embed Style Sheet</h1>
      </body>
  </html>
  ```
  + css는 html 문서 내에 포함시킬 수 있다 
  + **`<head>` 내부에서만 사용 가능**하고 `<style>` 태그를 사용해서 css코드 넣기
  + `<text/css>` MIME type 지정, 하지만 html 5 에서는 **생략 가능**




## CSS - [CSS 스타일 방법]
  + CSS 코드를 HTML 문서에 적용하여 스타일링하는 3가지 방법
    - 인라인 스타일 (inline style)
    - 인터널 스타일 (iternal style)
    - 익스터널 스타일 (external style)


### 인라인 스타일
  * 요소에 직접 스타일링을 추가하는 방법
    + 요소 내부에 style 속성을 이용하여 css 코드 작성

    ```html
    <html>
      <head>
        <link
        href="css/style.css" 
        type="text/css"   
        rel="stylesheet"     
        />
      </head>
      <body>
          <h1>Embed Style Sheet</h1>
      </body>
    </html>
    ```
    
    ```html
    <body>
    <section style="color: #903000">
    <h1 style="color: tan">
        <abbr 
        style="cursor: help; text-decoration: none" 
        </abbr>
     언어란?
    </h1>
    </body>
    ```
   
### 인터널 스타일
  *  CSS 코드를 HTML 문서에 포함

  ```html
  <head>
    <style>
      section {
        color: #903000;
      }
      h1 {
        color: tan;
      }
      abbr {
        cursor: help; 
        text-decoration: none;
      }
    </style>
  </head>
  ```

### ★익스터널 스타일★
   * CSS 파일을 HTML 문서에 연결
     = Link 요소를 사용하여 외부에 있는 css 파일을 적용하는 방법

   ```html
   <head>
   <link rel="stylesheet" href="css/style.css">
   </head>
   ```
   ```css
   section {
     color: #903000;
   }
   h1 {
     color: tan;
   }
   abbr {
     cursor: help; 
     text-decoration: none;
   }
   ```

## `<link>` 요소
  * 외부의 있는 문서를 연결할 때 사용
  * `<head>` 태그 안에 사용해야 한다. (중복된 `<link>`사용 가능)
  * `<link>``</link>` 형식이 아닌 `<link />` 형식으로 태그를 닫는다. 
  
    * `<rel>`속성 
      + 외부에서 불러오는 문서와의 관계를 설명하는 속성이다.
      `<link rel="stylesheet">` : 스타일 시트로써 문서를 불러오겠다는 의미다.

    * `<type>` 속성
      + link를 통해 연결된 문서의 MIME 유형을 나타낸다. 
        - css 파일일 경우 type="text/css"
        - js 파일일 경우 type="text/javascript"
        - xml 파일일 경우 type="application/txml"
      
      + MIME type이란?
        - 클라이언트에게 전송된 문서의 올바른 MIME 타입을 전송하도록 설정하는 것. 브라우저들은 리소스를 내려받았을 때 해야 할 기본 동작이 무엇인지를 결정하기 위해 대게 MIME 타입을 사용한다. 
        - MIME 타입은 대소문자를 구분하지는 않지만 대부분 소문자로 쓴다.
        - MIME 유형 : <https://www.sitepoint.com/mime-types-complete-list/>

    * `<href>` 속성
      + 연결될 문서를 불러오는 속성 
      + 상대경로와 절대경로
        - 상대경로 : 현재 머물고 있는 페이지에서 부터 시작해 경로를 설정하는 것
        - 절대경로 : 불러오려는 페이지를 가지고 있는 최상위 경로부터 시작해 설정하는 것
        - 예) 아래의 위치에 css와 html이 저장되어 있다고 가정한다면
          - /home/nana/one/style.css
            /home/nana/three/index.html
          - index.html의 위치에서 **상대** 경로로 css 파일을 불러올 때 : href="./one/style.css"
          - index.html의 위치에서 **절대** 경로로 css 파일을 불러올 때 : href="/home/nana/one/style.css"
            


## css 선택자
  * CSS는 HTML요소를 선택하는데 있어 다양한 선택자 옵션을 제공합니다. 

### 1) CSS 심플 선택자

#### 요소 선택자(Elements Type Selector) `figure { ... }`
  * 요소(타입, 태그) 선택자
  * HTML의 특정 요소를 선택해서 꾸며주는 것 
  * 우선권을 갖고 있음 
  * 항상 네트워크를 통해서 올바르게 CSS 파일을 불러왔는지 확인 

#### 그룹핑(Grouping) `a, abbr { ... }`
  * 그룹 선택자
  * 여러개의 요소(태그) 선택자를 콤마(,)를 사용해서 묶어주어 일괄적으로 디자인을 적용
  * 공통적으로 스타일을 적용하고 싶을 때는 요소 선택자를 묶어서 꾸며줄 수 있다. 

#### 전체 선택자(Universal Selector) `* { ... }`
  * `<*>` 별표 모양은 HTML에 존재하는 모든 요소를 가리킨다.모든 요소에 일괄적으로 스타일링을 주고자 할 때 사용

#### 자손 선택자(Descendent Selector) `h1 abbr { ... }`
  *포함하고 있는 요소를 꾸밀 때 사용

#### 클래스 선택자(Class Selector) `.class { ... }`
  * 앞의 `<.>`으로 구분 한다. .class (대소문자 구분하기 때문에 주의)
  * 예를 들어 ) 
    + `<.p.note>` : 클래스의 이름이 note인 요소를 찾는데 단락요소(p)가 클래스를 note를 가지고 있을 때 값에 적힌 디자인을 해라. 

#### 멀티 클래스 선택자(Mutil Class Selector) `.class1.class2 { ... }`
  * 1) .class1.class2 : 하나의 요소가 두 개의 class를 가진 형태
  * 2) .class1 .class2 : class1이라는 값을 가진 요소가 내부의 class2라는 요소를 찾을 때 사용(자손 선택자)
  * 3) 1과 2는 각각 다른 의미를 가진다. 

#### 아이디 선택자(ID Selector) `#id { ... }`
  * ID 값이 동일한 대상자를 찾음. 


### CSS 속성 선택자

#### 자식 선택자
  *  직계 자식만 포함, 손주는 포함 하지 않는다. 
  * 예시
 ```html
<head>
  <style type="text/css">
    body>blockquote {color:#4c6a77}
    p>img { ... }
    ul#subNav>li { ... }
  </style>
</head>
```

#### 속성 선택자
  * `*[] { ... }` : *요소가 [] 속성값을 가지고 있다면.
  * 연속해서 사용 가능 [], [] 두 가지 속성을 모두 갖고 있다.
  * [] 앞에는 생략 가능
  ```html
  div [id]    { ... }
    ex) <div id="anywayID">...
  p [class="note"] { ... }
    ex) <p class="note">...
  abbr [title~="mobile"] { ... }
    ex) <abbr title="Mobile Device">...
  img [ait|="love"] { ... }
    ex) <img alt="love-you" scr="love.jpg"/>

<!------------------------------>
  area [shape][title] { ... }

  <area shape="" coords="" href="">
  <area shape="" coords="" href="" title="">
  ```

#### 고급 속성 선택자
  * `<^>`: 해당 문자로 시작하는 것을 찾는다. 
  * `<$>`: 해당 문자로 끝나는 것을 찾는다
  * `<*>`: 어디에 있던지 문자를 포함하고 있는 것을 모두 찾는다. 
  * 예시
```html
a [href^="http://"]
  ex) <a href="http://naver.com/">...
a [href$=".psd"]
  ex) <a href="./data/displayBody.psd">...
abbr [title*="css"]
  ex) <img alt="htmlcssjavascript" scr="love.jpg"/>
```
### CSS 가상 클래스 선택자
 * `<a>` : 상태라는 의미를 가지고 있다
 * 콜론(:) 한 개 사용
```html
:link         { ... } 기본적으로 가지고 있는 상태
:visited      { ... } 방문한 상태 (보안상의 문제로 모든 속성을 사용할 수 없고 일부 속성만 사용 가능)

:hover        { ... } 마우스가 올라간 상태 (마우스 오버)
:active       { ... } 마우스로 클릭한 상태

:focus        { ... } 포커스가 된 상태 (탭키를 사용해서 선택된 상태, 마크업을 가장 마지막에 하는 것이 좋다)
:focus:hover  { ... } 포거스가 된 상태에서 마우스가 올라간 상태
:focus:active { ... } 포거스가 된 상태에서 마우스로 클릭한 상태

:first-child  { ... } 첫 번째 자식(대상을 선택하기 쉽게)
:last-child   { ... } 마지막 자식
:nth-child(n) { ... } 중간 자식 (처음과 마지막을 제외한)포뮬러 공식이 사용될 수 있다

:lang(ko)     { ... } 사용되는 언어에 따라 디자인을 적용 가능
```
### CSS 가상 요소 선택자
* 콜론(::) 두 개 사용
```html
    ::first-letter { ... } 단락의 첫 번째 글자
    ::first-line   { ... } 첫 줄 문자
    ::before       { ... } 
    ::after        { ... } 
```

# 4day

### Q & A

* Q ) class 란?

  + A ) 태그는 한 문서 안에서 여러번 사용할 수 있는데 이때 같은 이름을 가진 태그가 여러개일 경우, 태그에 이름(class 또는 id)를 부여해서 구체화 시킬 수 있다. class와 id의 차이는 사람의 이름과 주민등록 번호 같은 개념이다. 예를들어 홍길동은 class 개념이고 홍길동의 주민등록 번호는 id 개념이다. 홍길동은 다른 사람들도 쓸 수 있는 이름이고 홍길동의 주민등록 번호는 길동만 가질 수 있는 고유의 식별자이다.


### 컨테이너 요소(Container) : `<div>`, `<span>`
 * HTML 요소를 묶어주는 컨테이너 요소
  + 아무런 의미(semantic)는 가지지 않는다. 
  + 그러하무로 이 요소들은 적절한 시멘틱 요소가 없을 때 사용해야 한다. 

#### `<div>` 디비전(Divsion) 요소
 * 블록(block) 컨테이너(감싼다는 의미)
 * 단락이나 섹션 등 특정 범위를 묶는 용도로 사용

 ```html
<div class="division">
 ```

#### `<span>` 스펜(Span) 요소
* 인라인(inline) 요소
* 인라인 요소들(a, strong, em, b, i 등)을 감쌀 때 사용
* 블록 요소들(h1-6, p, blockquote, section 등)을 감쌀 수 없다.
* 숨김 텍스트를 마크업할 때 많이 사용한다. 

```html
<h2>
  SIX
  <span class="green ">C</span>
  <span class="yellow">O</span>
  <span class="orange">L</span>
  <span class="red   ">O</span>
  <span class="violet">R</span>
  <span class="blue  ">S</span>
</h2> 
```

## 텍스트 레벨 시멘틱 요소

### `<sub>` : 아래 첨자 (Subscript Text)
* `<dfn>` : definition 정의 요소
 ```html
   <dfn id="sulfuric-acid">
   H<sub>2</sub>SO<sub>4</sub>
   </dfn>
  ```
 ```html 
  참고
    <a id="이동위치이름">이동할 위치</a>
    <a href="#이동위치이름"> 위치 이동 클릭</a>
 ```
### `<sup>` : 윗첨자 (Super script)
* 윗첨자와 아래첨자를 구분하기 위해 `<div>`요소를 사용해 준다.
 ```html
 <sup><a href="#footnote-1">[1]</a></sup>
 ```
### `<mark>` : 관련 참조 목적의 하이라이트된 글자 요소
 ```html
<mark>삼각함수</mark>
 ```
### `<time>` : 기계가 이해할 수 있는 형태로 날짜나 시간을 나타내는 요소
```html
  <time datetime="2017-08-14T10:18">2017.08.14 10:18</time>
```
### `<abbr>` : 축약 요소
```html
<abbr title="맥도날드">맥날</abbr>
```
### `<s>` : 더 이상 관련이 없거나 더 이상 정확하지 않은 요소
```html
<s>11,900원</s> <em>50%</em> 5,900원
```

그룹핑(Grouping) 요소

* `<address>` 요소
  + `<a> href="tel:"` : 전화
  + 사람 또는 조직의 정보를 제공할 때 사용 (전화, 팩스, 주소 사업자 번호 등)
  + 조직의 저작자의 정보를 사용할 때는 `<small>`을 사용


* `<pre>` (Preserved text) 요소
  + 코드의 공백이나 줄바꿈을 보존한다. 
  + 이메일, 빈 줄이 표시된 단락, 글 머리표가 붙은 줄로 표시된 목록 등에 사용.
  + 컴퓨터 코드(언어) 표시 목적으로 사용.
  + 컴퓨터 코드, 출력, 키보드 블록을 나타내기 위해 pre 요소는 code, samp, kbd 요소와 함께 사용 가능.
  + ASCII 아트 표시.
  ```html
  <pre>
  ____  ∧ ∧
  |＼ /(´～`)＼<변화구
  |　|￣￣￣￣￣|
  |　|＝みかん＝|
   ＼|＿＿＿＿＿|
  </pre>
  ```
## 5day 

### CSS 상속
+ 브라우저 개발 툴에서 상속 여부를 확인

#### 상속되는 속성 (글자색, 글자 디자인에 관련된 것)
 + color
 + font-size
 + font-family
 + letter- spacing

#### 상속되지 않는 속성 (공간에 관련된 것)
 + outline
 + margin
 + border
 + padding

### 케스케이드(Cascade) 규칙
 + 정의 : 여러 스타일 시트를 결합하고 이들 사이의 충돌을 해결하는 프로세스
 + CSS는 케스케이드 개념이 중요하다는 것을 약어에서 강조, 가장 기본적인 수준에서는 규직 순서가 중요하지만 그보다 더 복잡하다는 것을 말한다. 

#### 중요성 (Importance)
  * !important 선언은 다른 모든 선언보다 우선권을 가진다.
  * !important 가 적용된 속성을 덮어 쓰려면. 다시 !important를 사용해야 하기에 최대한(절대!) 사용하지 않도록 노력해야 한다. (이 요소를 사용하지 않고 문제를 해결하려고 노력!)

#### 특성 (Specificity)
 * 선택자의 우선권에 대한 척도
 * 각 척도를 1, 10, 100, 1000 단위로 생각하면 이해하기 좋다.

```
    요소 선택자 < 클래스 선택자 < ID 선택자 < 인라인 스타일
     0,0,0,1        0,0,1,0       0,1,0,0       1,0,0,0
```

[NOTE]
```
*, >, +, ~ 등 콤비네이터(Combinators),
:not() 가상 클래스는 특성에 영향을 주지 않는다.
```

   [예시]
   ```
   *                           --0000 
   a                           --0001        
   a.link                      --0011
   li:nth-child(2) a:hover     --0022 
   .nav:nth-child(2) a:hover   --0031
   #outer a                    --0101
   #outer #inner a             --0201  
   style="color: tan"          --1000
                               --important
   ``` 

#### 소스 순서
 * 중요성, 특성이 설정되지 않았거나 동일한 경우 나중에 나온 소스의 스타일이 우선권을 가진다.

    예시
    ```
    p.note { color: #930212; }
    p { color: #d5727e; } // 우선권을 가진다.
    ```

## CSS - 타이포 그래피

### 폰트(Fonts) 스타일 속성
 * 폰트에 영향을 주는 속성으로 적용되는 모양, 크기, 굵기, 기울임 등
   + font-family 모양 
   + font-size 크기 
   + font-weight 굵기 
     - 
   + font-style 기울임 (이탤릭체)
   + font-variant 등.

 * 글자 색상은 color 속성으로 설정.
  +  color keywords 
     * red, gree, blue, pink, black
  +  hex color code 
     * #RRGGBB / 0 ~ 9, a ~ f 예)#1868a7
  +  rgb, rgba 
     * RED, GREEN, BLUE, ALPHA(투명도)    
       - 예)rgb(127,255,0), rgba(127,255,0,0.3)
       - 색상은 256가지색이 있다 (0 ~ 255)
       - 투명도: 0.0(투명) ~ 1.0(불투명)
       - rgba는 색상정보를 필요로 하는 속성에 직접 그 값을 부여할 수 있기 때문에 분리하여 사용할 수 있다. 
  +  hsl, hsla(hsl에 투명도 추가) 
     * HUE(색상), SATURATION(채도), LIGHTNESS(명도), ALPHA(투명도)
       - 예)hsl(360,60%,70%); , hsla(360,60%,70%,0.3);
       - HUE는 각도(deg)는 사용, 채도 및 명도는 퍼센트(%) 사용
       - 색상(0~360) : 360은 적색, 120 녹색, 240은 청색을 나타냄
       - 채도: 0%는 회색의 음영을 나타냄
       - 명도: 0%는 검정, 100% 하얀색을 나타냄

### CSS 투명도를 조절하는 속성 
  * `<opacity>` 
    + 0~1 사이의 값을 가진다
    + 숫자가 높아질수록 원본에 가깝고 숫자가 낮아질수록 투명해진다.
    + `opacity`는 부모요소에 적용시키면 자식들에게도 모두 상속되어 자식요소에서 해제할 수 없게된다. 그래서 배경과 텍스트를 따로 분리할 수 없는 문제가 생긴다. 이때문에 `opacity`를 0.8이하로 낮추지 않고 사용하는 경우가 많다.  

 *  웹브라우저는 운영체제가 지원하는 기본 폰트(웹 안전 폰트)만 화면에 렌더링 한다. (참고: https://cssfontstack.com) 즉, 사용된 폰트가 사용자 컴퓨터에 없으면 렌더링 X.   
 사용하기 전 안전한 폰트인지 확인!
```
  [웹 안전 폰트]
  Arial            [sans-serif]  고딕체
  Verdana          [sans-serif]  고딕체
  Courier New      [monospace]   코드체(공간이 동일)
  Georgia          [serif]       명조체
  Times New Roman  [serif]       명조체
  Trebuchet MS     [serif]       명조체
```
* 비주얼 디자인 과정에서 적용 가능한 웹폰트를 사용해야 한다. 폰트 저작권에 주의!

*
  + https://fonts.google.com
  + https://google.co.kr/search?q=무료+웹폰트

* `<local>` 속성 : 서버에서 다운받지 않고 사용자의 컴퓨터의 해당 폰트가 있으면 그 폰트를 사용해라.

### 텍스트(Text) 레이아웃 속성
* 텍스트 간격 및 레이아웃 기능에 영향을 주는 속성으로 행간, 자간, 어간, 정렬, 변형, 꾸밈, 그림자

 #### line-height 행간 
   - 최소 1.5이상이 글읽기에 용이하다.

 #### letter-spacing 자간 
   - px값 보다는 em단위로 설정하는것이 좋음.

 #### word-spacing 어간 (단어사이의 간격)
   - px, em(소수점) 단위 사용

 + 행간 > 어간 > 자간 - 가독하기가 쉬워짐.   
       

#### text-align 정렬 
 + left(기본값) / center / right
 + 속성 또한 부모로 부터 상속 받을 수 있다. 

#### text-indent 들여쓰기
 + 첫 번째 줄 라인만 들여쓰기 가능하다. 
 + padding-left를 사용하면 전체 들여쓰기 가능
 + em단위 사용(마이너스 값 사용 가능)

#### text-transform 변형 
 + uppercase(모두 대문자), lowercase(모두 소문자)

#### font-variant 변형 
 + small-caps(대문자만 크게, 소문자는 작은대문자) 
 + all-small-caps(모두 크기가 작은 대문자)
 + 영문에서만 사용, 한글을 적용 X

#### text-decoration 꾸밈 
 + underline(밑줄) : 판독의 어려움을 주기 때문에 권장하지 않음
 + overline(윗줄) 
 + line-through(중간줄)

#### white-space 공백처리

normal 기본값 : 공백 없이 그대로 유지
pre - 텍스트를 입력한 그대로 유지 
pre-line - 텍스트를 입력한 그대로 유지하면서 들여쓰기 제거
nowrap - 랩핑을 하지 않는다는 뜻, 한 줄로 길게 나타남

#### word-break - 단어의 분리를 어떻게 할 것인지 결정

 + break-all
  (공백/띄어쓰기) 수고했어.오늘도
  (음절)         수.고.했.어.오.늘.도

#### word-wrap : 박스의 가로 영역을 넘친 단어 내에서 임의의 분리 여부를 결정하여 줄바꿈에 관여
 + break-word

#### text-shadow 그림자
 + text-shadow : x y blur sprea color;
 ```
 text-shadow : 4px 4px 0px #9bdbde, 
               0px 3px 10px #943978;
 ```                
 + 그림자의 색상값을 멀티로 줄 수 있다. (콤마(,)로 구분)
 + 그림자를 적용하지 않은 글자가 가독성이 더 좋다


### 폰트 사이즈 단위

#### px, rem, em

  * px : 폰트의 크기를 고정하고 싶을 때 사용  
    + 모든 기기에서 동일한 사이즈로 고정, 브라우저의 크기가 작아져도 사이즈는 변하지 않는다. 
  
  * em : 앞서 적용된 폰트 크기의 배수로 적용됩니다.
    +  조상, 부모 요소가 정한 폰트의 크기를 기준으로 한다
  * 예시 
    + 부모의 폰트 사이즈가 30픽셀로 설정되어 있기 때문에 본문의 폰트사이즈는 2배수인 60픽셀로 적용된다. 
  
  * rem : em과 비슷하다. 웹 브라우저 기본 크기(16px)의 배수이다.  

  ```html
  <html>
  <style>
    body {
      font-size : 30px;
    }
     
     /* 폰트 사이즈는 30 * 2 = 60px이다 */
    p {
      font-size: 2em;
    }

     /* 폰트 사이즈는 16 * 2 = 32px이다 */    
    p {
      font-size: 2rem;
    }
  </style>

  <body>
    <p> Lorem ipsum dolor sit amet. </p>
  </body>
  </html>
  ```
  ```css

  ```

#### vw, vh
  * 반응형 웹의 폰트 사이즈 뿐만 아니라 행간이나 패딩등 다른 곳에서도 사용할 수 있다.  
  * vw : 1vw는 가로(Width)의 1/100. 너비 사이즈 변화에 따라 변한다.
    + 브라우저 화면의 너비에 따라 폰트 사이즈가 변화한다. 
    + 1000px * 1/100 = 10px(1vw)
    + 1vw(10px) * 2 = 2vw(20px)
    
  * vh : 1vh는 세로(Height)의 1/100. 높이 사이즈 변화에 따라 변한다
    + 브라우저 화면의 너비에 따라 폰트 사이즈가 변화한다. 

