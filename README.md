# EUID_UISD
<h1>1day</h1>

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

<!--밑에 3. 가 들여쓰기가 되어 있습니다. 
    위의 2. 과 위치를 맞추려면 어떻게 해야 하나요?-->

<h2>3. HTML 문서를 작성하는 기본 문법</h2>
 <ul>
  <li>웹 페이지는 헤드(head) 영역과 바디(body) 영역으로 구성된다.</li>
  <li>문서 타이틀(title)은 웹 페이지의 제목으로 브라우저 탭에 표시된다.</li>
 </ul>
 
<h3>HTML 용어</h3>
 <ul>
    <li>element : 요소</li>
    <li>open tag : 여는 태그</li>
    <li>tag : 닫는 태그</li> 
    <li>attribute : 속성</li>
    <li>value : 값</li>
 </ul>

<h3>기본 문법</h3>
 <ul>
    <li><여는태그> 컨텐츠 <닫는태그></li>
    <li><태그이름 속성="값"> 컨텐츠 <태그이름></li>
 </ul>
<!--코드 양식을 브라우저에 뜨게 하는 방법과 
    위의 목록과 아래의 목록 사이에 공간을 만드는 방법이 
    궁금합니다.-->
<ul>
  <li>P : 단락요소</>
  <li>title : 내부의 타이틀 속성</li>
  <li>Development Tools : 값 (내용 컨텐츠)</li>
  <li>P(Paragraph) 태그인 단락태그는 개발 도구(DevTools)이라는 컨텐츠를 감싸안고 있다.</li>
</ul>>

<h3>문서의 문자 인코딩을 설정</h3>

<!--<meta charset="utf-8">-->

<h2>4.콘텐츠를 감싸지 않는 요소</h2>
 <ul> 
  <li>
    empty element (콘텐츠를 감싸지 않는 요소) : 닫는 태그가 없다, 내용이 비어있다는 의미
  </li>
 </ul>

<h3>meta 요소는 왜 닫는 태그가 없는가?</h3>
 <ul>
  <li>내용 컨텐츠를 감싸지 않았기 때문이다 (내용 x)</li>
  <li>여는 태그 만으로서 정보를 제공할 수 있는 요소이다</li>
 </ul>

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


<h3>들여쓰기</h3>
 <ul>
    <li>이를 통해 계층 구조를 시각적을 표현한다.</li>
    <li>반드시 필요한 것은 아님, 보기 편하게 하려고 하는 것</li>
    <li>들여쓰기를 하지 않아도 웹브라우저에 나타나는 것은 똑같음</li>
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

<!--<html lang=”ko-KR”>-->

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

 
<h2>8. HTML 이미지 & 피규어 & 캡션</h2>

<h3>이미지 (images)</h3>

<!--<img src =”소스테이터” alt=”대체텍스트”>-->
<ul>
  <li>souce : src</li>
  <li>alterate test : alt</li>
  <li>대체 텍스트 : 이미지의 경로가 잘못됐거나 
    서버에 올려진 이미지가 깨졌을 경우에 
    대치되는 텍스트를 출력하는 경로이다.</li>
</ul>


<h3>HTML 문서는 이미지를 포함시키지 않는다</h3>
<lu>
  <li>한글이나 워드는 문서에 이미지를 포함시키지만 
    HTML 문서는 이미지를 포함시키지 않는다.</li>
   <li>이미지를 연결해서 사용한다.</li>
   <li>HTML 파일에 이미지가 포함이 된다면 파일의 용량이 커지기 때문에 속도가 느려진다.</li>
</lu>

<h3>캡션 (Caption)</h3>
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


<h2>10. HTML 목록 디자인</h2>
<ul>목록(List)
  <li>순차 (ordered) : ul</li>
  <lI>비순차 (unordered) : ol</lI>
</ul>

<ul>
  <li>목록 아이템 (List Item)</li>
  <li>li은 ul, ol 안에 들어갈 수 있다.</li>
</ul>

<!--<li> </lu>-->


<h1>2day</h1>

<h2>질문</h2>
<p>1) 문법이나 속성을 코드로 메모하는 방법을 모르겠습니다.</p>
<p>2) 예를들어 위의 방법을 궁금해서 MDN 사이트를 이용한다고 할 때
  어떤식으로 검색을 해야하는 지 모르겠습니다.
  '코드', '속성'등의 키워드로 검색을 해도 원하는 정보를 얻기가 쉽지가 않네요... 이용법을 검색해도 잘 안나오고요.. 
</p>


<h2>1.하이퍼링크</h2>
 <h3>앵커와 하이퍼링크</h3>

 <ul>
  <li>앵커(anchor)</li>
   <ul>
    <li>같은 페이지에서 이동</li>
    <li>다른 페이지나 같은 페이지의 어느 위치, 파일, 이메일 주소와 그 외 다른 URL로 연결할 수 있는 하이퍼링크를 만든다.</li>
   </ul>
 </ul>

 <ul>
  <li>하이퍼링크(hyperlink)</li>
   <ul>
    <li>페이지가 변하면서 이동하는 것 </li>
    <li>tel: URL을 사용하는 전화번호</li>
    <li>mailto: URL을 사용하는 이메일 주소</li>
   </ul>
 </ul>

 <h3>웹 문서에 URL을 입력하는 방법</h3>
  <ul>
   <li>절대경로 (absolute path)</li>
    <ul>
     <li>현재 HTML 문서와 상관없이 URL 주소를 사용해 리소스를 찾는 것</li>
    </ul>
  </ul>

  <ul>
   <li>상대경로 (relative path)</li>
    <ul>
     <li>현재 HTML 문서에서 상대적인 위치를 설정하는 것</li>
    </ul>
  </ul>

  <ul>
   <li>루트 상대경로 (root-relative path)</li>
    <ul>
     <li>현재 HTML 문서가 존재하는 영역의 최상위 루트 경로에서 대상을 찾는 것</li>
    </ul>
  </ul>

<h2>2.설명목록</h2>

<ul>
 <li>설명목록(Description List) : dl</li>
  <ul>
  <li>설명하는 것들을 묶어주는 그룹 역할</li>
  </ul>
 <li>용어(Description Term) : dt</li>
   <ul>
  <li>내부에 해당하는 용어</li>
  </ul>
 <li>기술(Description Description) : dd</li>
   <ul>
  <li>그 용어를 설명하는 역할</li>
  </ul>
</ul>

<!-- 
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
-->
 
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

# 3day

## CSS(Cascading Style Sheets)

CSS는 HTML 문서를 스타일링 하는 언어이다
 
## 1. css 기본 문법

```html
  선택자 {
    속성1: 값;
    속성2: 값2;
  }
```
```html
 h1 {
   color: deepskyblue;
   font-size: 2em;
 }
```

+ css는 html 문서 내에 포함시킬 수 있다 
+ `<head>` 내부에서만 사용 가능하고 `<style>` 태그를 사용해서 css코드 넣기
+ MIME type을 지정하는데 HTML5에서는 기본 생략
  
 

### 스타일 방법 3가지

```html 
<link
  href="css/style.css"
  type="text/css"
  rel="stylesheet"
/>
```

+ 인라인 스타일
   * 요소 내부에 style 속성을 이용하여 css 코드 작성
   ```html
   <section style="color: #903000; text-decoration: none:">
   ```

+ 인터널 스타일
  ```html
  <style>
   section {
    color: #903000;
   }
  </style>
  ```

+ 익스터널 스타일
   * Link 요소를 사용하여 외부에 있는 css 파일을 적용하는 방법
   ```html
   <link rel="stylesheet" href="css/style.css">
   ```

## 2.css 선택자

### 1) CSS 심플 선택자

#### 요소 선택자(Elements Type Selector) `figure { ... }`
  * 문서 내의 특정 요소를 선택해서 편집 가능 
  * 우선권을 갖고 있음 

#### 그룹핑(Grouping) `a, abbr { ... }`
  * 공통적으로 스타일을 적용하고 싶을 때는 요소 선택자를 묶어서 꾸며줄 수 있다. 

#### 전체 선택자(Universal Selector) `* { ... }`
  * *를 사용한다 
  * 모든 요소에 스타일을 적용할 수 있다. 

#### 자손 선택자(Descendent Selector) `h1 abbr { ... }`
  *포함하고 있는 요소를 꾸밀 때 사용

#### 클래스 선택자(Class Selector) `.class { ... }`
  * .class (대소문자 구분하기 때문에 주의)

#### 멀티 클래스 선택자(Mutil Class Selector) `.class1.class2 { ... }`
  * 1) .class1.class2 : 하나의 요소가 두 개의 class를 가진 형태
  * 2) .class1 .class2 : class1이라는 값을 가진 요소가 내부의 class2라는 요소를 찾을 때 사용(자손 선택자)
  * 3) 1과 2는 각각 다른 의미를 가진다. 

#### 아이디 선택자(ID Selector) `#id { ... }`
  * ID 값이 동일한 대상자를 찾음. 


### CSS 속성 선택자

#### 자식 선택자
  *  직계 자식만 포함, 손주는 포함 하지 않는다. 

#### 속성 선택자
  * `*[] { ... }` : *요소가 [] 속성값을 가지고 있다면.
  * 연속해서 사용 가능 [], [] 두 가지 속성을 모두 갖고 있다.
  * [] 앞에는 생략 가능
  ```html
  [id]    { ... }
  [class] { ... }
  [title] { ... }
  [shape] { ... }

  area[shape][title] { ... }

  <area shape="" coords="" href="">
  <area shape="" coords="" href="" title="">
  ```
  * 단어가 반드시 일치해야 한다. 
  ```html
  [id="about-css"] { ... }
  #about-css       { ... }

  [class="note"] { ... }
  .note
  ```

### CSS 가상 클래스 선택자
 * `<a>` : 상태라는 의미를 가지고 있다
 * 콜론(:) 한 개 사용
```html
:link         { ... } 기본적으로 가지고 있는 상태
:visited      { ... } 방문 상태 

:hover        { ... } 마우스가 올라간 상태
:active       { ... } 마우스로 클릭한 상태

:focus        { ... } 포커스가 된 상태
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

