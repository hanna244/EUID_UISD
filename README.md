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
<ul>

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
 <lu>
    <li><여는태그> 컨텐츠 <닫는태그></li>
    <li><태그이름 속성="값"> 컨텐츠 <태그이름></li>
 </lu>
<!--코드 양식을 브라우저에 뜨게 하는 방법과 
    위의 목록과 아래의 목록 사이에 공간을 만드는 방법이 
    궁금합니다.-->
<lu>
  <li>P : 단락요소</>
  <li>title : 내부의 타이틀 속성</li>
  <li>Development Tools : 값 (내용 컨텐츠)</li>
  <li>P(Paragraph) 태그인 단락태그는 개발 도구(DevTools)이라는 컨텐츠를 감싸안고 있다.</li>
</ul>>

<h3>문서의 문자 인코딩을 설정</h3>

<!--<meta charset="utf-8">-->

<h2>4.  콘텐츠를 감싸지 않는 요소</h2>
 <lu> 
  <li>
    empty element (콘텐츠를 감싸지 않는 요소) : 닫는 태그가 없다, 내용이 비어있다는 의미
  </li>
 </lu>

<h3>meta 요소는 왜 닫는 태그가 없는가?</h3>
 <lu>
  <li>내용 컨텐츠를 감싸지 않았기 때문이다 (내용 x)</li>
  <li>여는 태그 만으로서 정보를 제공할 수 있는 요소이다</li>
 </lu>

<h2>5. 표준 호환모드</h2> 
 <lu>  
  <li>HTML 요소 간 관계(부모, 자식, 형제)가 있다.</li>
  <li>HTML element 는 root element로 모든 요소의 조상이 될 수 있다.</li>
  <li>HTML element
     <lu>
        <li>head : first child</li>
        <li>body : last child</li>
     </lu>
  </li>
  <li>각 요소 사이에는 어떠한 것도 들어 올 수 없다.</li>
</lu>


<h3>들여쓰기</h3>
 <lu>
    <li>이를 통해 계층 구조를 시각적을 표현한다.</li>
    <li>반드시 필요한 것은 아님, 보기 편하게 하려고 하는 것</li>
    <li>들여쓰기를 하지 않아도 웹브라우저에 나타나는 것은 똑같음</li>
 </lu>

<h3>DOCTYPE (document. Doctype)</h3>
 <lu>
    <li>표준모드와 비표준모드를 설정</li>
    <li>웹 표준 문서이자, 모든 문서에서 호환되는 문서가 된다.(표준모드)</li>
    <li>만약 DOCTYPE 없다면 해당 문서는 비표준 문서가 된다.</li>
    <li>페이지의 가장 상위에 존재해야 한다.</li>
    <li>소문자, 대문자 구분 x</li>
    <li>대부분의 웹브라우저에서 표준모드를 사용하기 때문에 DOCTYPE을 사용해서 페이지를 작성하는 것이 좋다.</li>
</lu>

<h2>6. 문서에 사용되는 주 언어 설정</h2>

<!--<html lang=”ko-KR”>-->

<h2>7. 제목과 단락</h2>

<h3>단락(Paragraph)</h3>
 <lu>
   <li>사용자가 가장 많이 읽는 콘텐츠는 단락(Paragraph)입니다. 단락은 p 요소로 구성됩니다.</li>
   <li>글의 덩어리를 나눌 때 단락을 사용함</li>
</lu>


<h3>제목(Headings)의 단계</h3>
 <lu>
  <li>제목 레벨 : 1 ~ 6단계
    <lu>
      <li>1단계는 문서에서 하나만 작성 </li>
      <li>2단계부터는 여러 개의 제목을 사용할 수 있다.</li>
    </lu>
  
</lu>

<h3>주석(Comments)</h3>
 <lu>
   <li>HTML 주석은 브라우저에서 해석되지 않습니다.</li>
</lu>

 
<h2>8. HTML 이미지 & 피규어 & 캡션</h2>

<h3>이미지 (images)</h3>

<!--<img src =”소스테이터” alt=”대체텍스트”>-->
<lu>
  <li>souce : src</li>
  <li>alterate test : alt</li>
  <li>대체 텍스트 : 이미지의 경로가 잘못됐거나 
    서버에 올려진 이미지가 깨졌을 경우에 
    대치되는 텍스트를 출력하는 경로이다.</li>
</lu>


<h3>HTML 문서는 이미지를 포함시키지 않는다</h3>
<lu>
  <li>한글이나 워드는 문서에 이미지를 포함시키지만 
    HTML 문서는 이미지를 포함시키지 않는다.</li>
   <li>이미지를 연결해서 사용한다.</li>
   <li>HTML 파일에 이미지가 포함이 된다면 파일의 용량이 커지기 때문에 속도가 느려진다.</li>
</lu>

<h3>캡션 (Caption)</h3>
<lu>
  <li>캡션은 이미지와 묶여서 하나의 덩어리가 되어야 한다.</li>
  <li>피규어(Figure)요소를 사용해서 이미지와 캡션 요소를 하나도 감쌀 수 있다.</li>
</lu>


<h3>피규어(Figure)</h3>
<lu>
  <li>도표, 차트, 이미지, 표를 감쌀 때 사용되는 요소</li>
  <li>피규어 요소 안에 피그캡션 요소를 넣어 줄 수 있다.</li>
</lu>

<h2>9. 문법 검사</h2>

<p>검사 사이트 (http://validator.w3.org/)
  엔티티 코드 (http://entitycode.com/)</p>


<h2>10. HTML 목록 디자인</h2>
<lu>목록(List)
  <li>순차 (ordered) : lu</li>
  <lI>비순차 (unordered) : ol</lI>
</lu>

<lu>
  <li>목록 아이템 (List Item)</li>
  <li>li은 ul, ol 안에 들어갈 수 있다.</li>
</lu>

<!--<li> </lu>-->
