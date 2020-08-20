# EUID_UISD

# 1day

## 임베디드(Embedded) 요소

## HTML 픽쳐(Picture) 요소

  * **0개 이상의 `<source>` 요소**와 **1개 이상의 `<img>`**를 포함하는 컨테이너 요소.
  * 다양한 스크린 환경(스마트폰, 테블릿, 데스크탑 등)에 맞는 적합한 이미지를 제공하기 위한 목적으로 사용.
  * `<source>` 요소를 사용할 수 없을 경우, `<img>` 요소가 화면에 표시.

  ```html
  <img> 요소
  - HTML 문서에 이미지를 포함(링크)
  
  [속성]
  src    - 이미지 파일 경로 설정
  alt    - 이미지 대체 텍스트 설정
  width  - 이미지 너비 설정
  height - 이미지 높이 설정
  usemap - 이미지 맵 연결 설정
  ```

## `<source>` 요소
  + `<picture>`, `<audio>`, `<video>` 요소의 **다중 미디어 리소스를 지정**하기 위해 사용.
  + 중첩 가능한 요소
  + `<srcset>`속성을 가짐 
    + `<img>`요소의 `<src>`속성과는 같지 X
  + `<media>`속성을 사용해서 media queries 구문을 사용할 수 있다
    + media queries 구문?  
    스마트폰, 테블릿, 데스크탑을 구분해 줄 수 있는 코드 구문

  ```html
          media 속성:
          <picture>
            <source srcset="bamboo-pen.png" media="(min-width: 600px)"> (좀 더 큰 이미지)
            <img src="bamboo-pen-narrow.png" alt="Bamboo Pen"> (작은 이미지)
          </picture>  

          type 속성:
          <picture>
            <source srcset="bamboo-pen.svg" type="image/svg+xml"> (1)
            <img src="bamboo-pen-narrow.png" alt="Bamboo Pen">
          </picture>  

          * type은 이미지 형식에 따라 변경
            - <source type="image/png">
            - <source type="image/jpeg">
            - <source type="image/svg+xml">
  ```
  * (1) `<svg>`, `<png>`, `<jpeg>` 등 여러 확장자를 사용할   때  브라우저가 올바르게 인식할 수 없다는 판단이 든다면
  mime type을 지정해서 미디어 타입을 설정한다.  

  ```html
    <!-- img + picture + source -->  

  <picture>
    <source srcset="media/image/kitten-large.png" type="image/png" media="(min-width: 900px)">
    <source srcset="media/image/kitten-medium.png" type="image/png" media="(min-width: 600px)">
    <img src="media/image/kitten-small.png" alt="작은 고양이"
  </picture>
  ```
  * min-width : 최소 가로폭
  * `<midea>`속성을 사용해서 반응형 웹을 만들 수 있다  


## HTML 비디오(Video) 요소

  * `<video>` 요소
    + 동영상 콘텐츠를 HTML 문서에 포함하기 위해서 사용.
    + src 속성이나 <source> 요소을 이용해 여러 개의 동영상 소스 중 하나를 표시. (현재는 mp3, mp4가 모든 브라우저에 지원되기 때문에 `<souce>`를 사용 X)

  [속성]   
  `<src>`      - 비디오 파일 경로   
  `<poster>`   - 포스터 이미지 경로 (poster요소가 없을 경우 비디오의 첫 화면이 나옴)   
  `<preload>`  - 사용자 경험 향상(메타데이터 / 비디오 다운로드)에 관한 설정    
  [none, metadata, auto(기본 값)]   
  `<controls>` - 재생 컨트롤 표시 설정   
  `<autoplay>` - 자동 재생 설정   
  자동재생은 가급적 사용 X (굳이 사용한다면 `<muted>`속성을 사용하여 음소거)    
  `<loop>`     - 반복 설정   
  `<muted>`    - 음소거 설정   
    * 
      + `<src>`, `<poster>` : 값이 반드시 필요하다  
      + `<preload>`, `<controls>`, `<autoplay>`, `<loop>`, `<muted>` : 값이 반드시 필요하지 않다. 

  
  자동재생은 가급적 사용 X (굳이 사용한다면 `<muted>`속성을 사용하여 음소거) 

  ```html
  [사용 예시]
  <video src="videofile.mp4" poster="posterimage.jpg">
  HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
  <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
  </video>
  ```

  ```html
  <!-- video + track -->
  <video 
  src="media/video/holzweiler.mp4" 
  poster="media/video/holzweiler-short_cover.png"
  autoplay
  loop="true"
  muted="true"
  >

    <p>
      HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
      <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
    </p>
  </video>
  ```

## HTML 오디오(Audio) 요소

  * `<audio>` 요소
    + 동영상 콘텐츠를 포함하기 위해서 사용.
    + src속성이나 <source> 요소을 이용해 여러개의 동영상 소스를 표시. (현재는 mp3, mp4가 모든 브라우저에 지원되기 때문에 `<souce>`를 사용 X)

  [속성]
  `<src>`      - 오디오 파일 경로   
  `<volume>`   - 볼륨 조절(0.0 ~ 1.0)   
  `<muted>`    - 음소거 설정   
  `<poster>`   - 포스터 이미지 경로   
  `<preload>`  - 사용자 경험 향상(메타데이터 / 비디오 다운로드)에 관한 설정    
  [none, metadata, auto]   
  `<controls>` - 재생 컨트롤 표시 설정   
  `<autoplay>` - 자동 재생 설정   
  `<loop>`     - 반복 설정   

  ```html
  [사용 예시]
  <audio src="audiofile.mp3">
  HTML5 <code>audio</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
  <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a>로 업데이트 하세요.
  </audio>
  ```
  ```html
  <!-- audio -->
  <figure style="margin: 0;"> (`<margin>` 여백 없음)
    <img  
    src="media/audio/tobu-Itro_Cloud9--cover.jpg"
    alt="cloud9 - todu & itro" width="300" height="300">
  <figcaption>
    <audio src="media/audio/tobu-Itro_Cloud9.mp3" controls autoplay>
      <p>
        HTML5 <code>video</code> 요소를 지원하지 않는 구형 웹 브라우저를 사용 중입니다.
        <a href="http://outdatedbrowser.com/ko">최신형 브라우저로 업데이트</a> 하세요.
      </p>
    </audio>
  </figcaption>
</figure>
  ```

## HTML 트랙(Track) 요소
  * 비디오/오디오 재생 시, 자막을 표시.
  * `<default>` 
    + 속성을 설정하지 않을 경우, 자막 사용 안함 됨
    + 자막 언어 고정 가능

  ```html
  [사용 예시]
      <video src="videofile.mp4" poster="posterimage.jpg">
        <track kind="subtitles" src="videofile.ko.vtt" srclang="ko" label="한국어" default>
        <track kind="subtitles" src="videofile.en.vtt" srclang="en" label="English">
      </video>

      <audio src="audiofile.mp3">
        <track kind="subtitles" src="audiofile.ko.vtt" srclang="ko" label="한국어">
        <track kind="subtitles" src="audiofile.en.vtt" srclang="en" label="English">
      </audio>
  ```

  ```html
    <!-- video + track -->
  <video 
  src="media/video/The temperature of dating.mp4" 
  controls>
    <track 
    kind="subtitles"
    src="media/video/vtt/The temperature of dating.ko.vtt"
    srclang="ko"
    label="한국어">
    <track 
    kind="subtitles"
    src="media/video/vtt/The temperature of dating.en.vtt"
    srclang="en"
    label="영어"
    default>
  </video>

  ```

## HTML 인라인 프레임(iframe) 요소

  * 인라인 프레임(Inline Frame)에 다른 HTML 페이지를 포함하여 화면에 표시.

  [속성]  
  `<src>`             - 프레임 소스 설정  
  `<width>`          - 프레임 너비 설정  
  `<height>`          - 프레임 높이 설정  
  `<allowfullscreen>` - 프레임 전체화면 설정  
```html
      [사용 예시]
      <iframe
        width="560"
        height="315"
        src="https://www.youtube.com/embed/0wlXaHmmOVc?rel=0&amp;showinfo=0"
        allow="autoplay; encrypted-media"
        allowfullscreen></iframe>

      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d12643.636820892792!2d127.01610674058901!3d37.60429582641849!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357cbc91e5ca4f03%3A0x18820a16e406c8ea!2z7ISc7Jq47Yq567OE7IucIOyEseu2geq1rCDquLjsnYwx64-ZIDUzMC0zNg!5e0!3m2!1sko!2skr!4v1520001155674" width="600"
        height="450"
        style="border: 0"
        allowfullscreen></iframe>
```
```html
  <!-- iframe -->
          <iframe 
    width="560" 
    height="315" 
    src="https://www.youtube.com/embed/0wlXaHmmOVc" 
    frameborder="0" 
    allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" 
    allowfullscreen>
    </iframe>

        <iframe 
    src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d6324.212923431429!2d127.0002682!3d37.5761107!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x357ca2e2c8102391%3A0x51d36941638dd458!2sDobbit!5e0!3m2!1sko!2skr!4v1597675479744!5m2!1sko!2skr" 
    width="600" 
    height="450" 
    frameborder="0" 
    style="border:0;" 
    aria-hidden="false" 
    tabindex="0">
    </iframe>
```
## HTML 이미지 맵(map) 요소

### `<map>` 요소
  * 이미지 맵(클릭 가능한 링크 영역)을 정의하기 위해 <area>와 함께 사용됨.
  * 이미지 맵 좌표 생성: https://www.image-map.net/

### `<area>` 요소
  * 이미지의 핫스팟 지역 정의, 하이퍼링크 설정. <map> 내부에서만 사용 가능.
  * 여러개 사용 가능 (원, 사각형, 다각형)
  * **`<alt>`(필수)**, `<title>` 성분을 사용해 주기

  [속성]  
  `<shape>`    - 핫스팟 모양 설정  
  `<coords>`   - 모양의 좌표 값 설정  
  `<href>`     - 하이퍼링크 주소 설정  
  `<target>`   - 새 창(탭) 열림 설정   
  `<alt>`      - 대체 텍스트 설정  
  `<hreflang>` - 연결된 페이지의 언어 속성 설정  
  `<download>` - canvas 데이터 다운로드 설정  
```html
      [사용 예시]
      <img src="products-map.jpg" alt="제품 모음" usemap="#products-map">
      <map name="products-map">
        <area
          shape="circle"
          coords="200,250,25"
          hreflang="en-GB"
          href="another.html"
          alt="Another Page"
          target="_blank">
      </map>
```

```html
  <!-- map + area -->
    <img 
    usemap="#foods-in-kr"
    src="media/image/food-in-korea-of-republic.jpg" 
    alt="우리나라 길거리 음식도감">

  <map name="foods-in-kr">
    <area shape="rect" coords="0, 0, 100, 100"
    href="http://www.typographyseoul.com/news/detail/404">
  </map> 
```

## HTML 확장 가능한 벡터그래픽(SVG) 요소
  * 확장가능한 벡터 그래픽(SVG)은 2차원의 벡터 그래픽을 기술하기 위한 XML 마크업 언어.
  * `<SVG>` 요소는 내용이 상당히 방대하다
  * 이미지를 직접적으로 삽입하는 것과 svg요소를 사용하여 그림을 삽입하는 것 차이
    + 이미지를 svg에 연결시키는 경우는 css 코드를 이용해서 디자인을 변경 할 수 없다
    + 직접적으로 코드를 따라서 그래픽에 있는 디자인을 변경하려면 svg를 문서내에 직접 삽입을 해야한다.  

      ```html
      [예시 코드]
      <img src="svgfile.svg" alt="SVG File">

      <svg width="150" height="150" viewBox="0 0 150 150">
        <circle r="50" cx="75" cy="75" fill="#333" stroke="#900" stroke-width="4"; />
      </svg>
      ```
---
# 2day

  * GUI, CLI란?
    + GUI (그래픽 유저 인터페이스)
      - 그래픽 환경으로 시스템 제어 (우리가 마우스로 클릭하며 사용하는 것) 

    + CLI (커맨드 라인 인터페이스)
      - 명령어를 통해 시스템 제어 (예: Bash)
        + Bash    
        각 운영 체제가 다른 컴퓨터에서 같은 명령어로 컴퓨터를 조작? 할 수 있는 프로그램?
          - cd (Change-Directoyr) : 지정한 경로로 이동
          - ls (List) : 폴더 목록 보기

  * Git 이란?    
   버전 관리 시스템(VCS), 무료, 공개 소프트웨어 
    |이름| 설명|
    |---|---|
    |Tracked|관리대상임|
    |Untracked|관리대상이 아님|
    |Modified|수정함|
    |Unmodified|수정하지 않음|
    | Staged|커밋으로 저장소에 기록|   
    |soft |현재 인덱스, 워킹 트리를 유지한 채로 HEAD를 변경|
    |mixed| default 옵션. 인덱스는 취소한채로 워킹트리만 그대로|
    |hard |인덱스와 워킹트리 변화를 모두 제거하고 HEAD를 변경|
    |Gitlog|Git 기록|
    |브랜치(Branch)|새로운 가지를 뻗는 것을 의미, 기존 개발에 이어서 작업하지 않고 새롭게 가지를 쳐서(브랜치) 작업할 수 있다.|
    |머지(Merge)|각각의 브랜치에서 작업한 코드를 합치는 기능|

    + Git 사용 중 자주 만나는 이슈 정리 : <https://parksb.github.io/article/28.html>


  * GitHub   
   코드저장소(Git)을 웹에 옮겨 놓은 원격저장소
    + 프로젝트를 관리할 때 사용하기 좋음. (여러사람이 참여하여 수정 가능) 
    + 분산버전관리    
     파일 변화를 시간에 따라 기록, 특정 시점의 버전을 다시 가져올 수 있다.
      - 코드 변경 이력 확인 가능, 코드 복구 가능
      - 코드 이전 이력과 비교 가능
    + <https://aonee.tistory.com/15>


## [CSS] 박스 모델

## [BLOCK vs INLINE]
   * block level 요소 (Flow Contents : HTML5)
   * inline 요소 (Phrasing Contents : HTML5)
        
  + 블록 박스
    - 블록 박스는 다른 블록 박스에 포함되거나, 포함할 수 있고, **너비(width)/ 높이(height) 설정이 가능**합니다. 내부에 콘텐츠를 포함하지 않을 경우 높이는 0입니다.
        - 컨텐츠의 남은 여백까지도 박스로 채워진다. 
          그래서 글자의 정렬(왼쪽, 가운데, 오른쪽)을 설정할 
          수 있다

  + 인라인 박스 
    - 인라인 박스는 인라인 박스에 포함되거나, 포함할 수 
          있지만, **블록 요소는 포함할 수 없습니다.**(컨텐츠의 라인까지만 박스가 채워진다.)   
          **너비(width)/ 높이(heght) 설정이 가능하지 않습니다. 내부에 포함한 콘텐츠만 높이와 너비를 가지게 됩니다.**

  + 인라인 블록 박스 
    - 인라인 블록 박스는 기본적으로 인라인처럼 화면에 렌더링되지만, 블록박스처럼 너비(width)/ 높이(heght) 설정이 가능합니다. 
        (`<img>`, `<input>`, `<button>` 등)
    ```css
    <!--display요소로 inline, block, inline block 설정 가능-->
    .inline-block-box {
      display: inline; 
      width: 200px;
    }
    ```
    * display요소로 inline, block, inline block 설정 가능
      + display: inline     
      display: block     
      display: inline block     
        
      
  * 공부 할 때 각 요소를 선택해서 display 값을 확인하면 된다.
      ```
      [block 요소들]
        - address
        - article
        - aside
        - audio
        - blockquote
        - canvas
        - dd
        - div
        - dl
        - fieldset
        - figcaption
        - figure
        - footer
        - form
        - h1~6
        - header
        - hr
        - noscript
        - ol
        - output
        - p
        - pre
        - section
        - table
        - tfoot
        - ul
        - video
      ```

## [BOX]
  * margin-box   --  외부 공간 박스
  * border-box   --  테두리 공간 박스
  * padding-box  --  내부 공간 박스
  * content-box  --  콘텐츠 공간 박스
    + margin-box : 투명한 영역(배경색 X), 박스와 박스 사이의 간격을 제어할 때 사용, 음수값 사용 가능(-10px, -20px..)
    + border-box : 박스 테두리 모양을 치고 싶을 때 사용 (음수값 X)
    + padding-box : 박스 안쪽에 공간 여백을 줄 때 사용 (음수값 X)
    + border-box, padding-box, content-box : 배경색 적용 가능
    
  * 인라인 박스는 좌/우 방향으로 마진,패딩 공간을 설정할 수 있으나, **상/하 방향으로는 공간이 설정되지 않습니다.**
    + 패딩 공간을 설정 패딩이 적용된 것 처럼 보이나 패딩으로 인한 공간이 벌어지지 않는다.

  ### [margin]
   * margin-top
   * margin-right
   * margin-bottom
   * margin-left
      + 시계 방향 순 (t r b l)
   * `margin: t r b l` 모든 방향 값이 다름
   * `margin: t r b (l=r)`    
  위/아래 값을 다르게 줄 때, left값이 right값을 상속 받음
   * `margin: t r (b=t) (l=r)`    
   위/아래, 좌/우 값이 동일, bottom값이 top값을 상속 받음
   * `margin: t (r=t) (b=t) (l=r)` 모든 방향 값이 동일

  ### [border]
  ```
    * border-(top|right|bottom|left)-width
    * border-(top|right|bottom|left)-style
    * border-(top|right|bottom|left)-color
    * border: width style color (모든 방향 값을 설정)
    * border-top: width style color 
    * border-right: width style color
    * border-bottom: width style color
    * border-left: width style color
  ```

  ### [padding] 
   * [margin]과 같은 작동 원리로 동작함
  ```
    * padding-top
    * padding-right
    * padding-bottom
    * padding-left
    * padding: t r b l
    * padding: t r b (l=r)
    * padding: t r (b=t) (l=r)
    * padding: t (r=t) (b=t) (l=r) 
  ```

  ```css
  .demo {
    width: 100px;
    height: 100px;
    background: #eee;
    text-align: center;
    line-height: 100px; (줄 높이를 정하는 속성)
    margin: 20px 10px 10px 15px;
    padding-top: 1em;
    border-bottom: 1em double #6d70d2;
  }
  ```
   * border 테두리 지정 : <https://www.tabmode.com/homepage/border.html#gsc.tab=0>

  #### `text-align` 속성 
   * 텍스트의 정렬 방향을 의미합니다.
      + left: 왼쪽 정렬    
        right: 오른쪽 정렬     
        center: 중앙 정렬    
        justify: 양쪽 정렬 (자동 줄바꿈시 오른쪽 경계선 부분 정리)

      ```css
      #box1 { text-align: right; }
      #box2 { text-align: left; }
      #box3 { text-align: center; }
      ```

```css
      .dimension-ex {
  min-width: 200px;
  min-height: 80px;
  max-width: 500px;
  max-height: 120px;
}
```
  
## [DIMENSION]
  * width       --  박스 너비
  * height      --  박스 높이
  * min-width   --  박스 최소 너비
  * min-height  --  박스 최소 높이
  * max-width   --  박스 최대 너비
  * max-height  --  박스 최대 높이

  ### [BOX SIZING]
   * content-box
   * border-box

     - content-box (default):  
      width = content-box  
      height = content-box

     - border-box:  
        width = content-box + padding-box + border-box  
        height = content-box + padding-box + border-box  

        ```css
        box-sizing: border-box;
        box-sizing: content-box;
        ```

       ```css
       .box-sizing { 
         box-sizing: border-box, content-box;
         width: 200px; 
         height: 100px;
         border: 1px solid;
         text-align: center;
         line-height: 100px;
       }
       ```



  ### [FLOW]
   * `overflow`  --  박스를 넘쳐난 상태(흐름) 조정   
   부모 박스의 영역을 자식 박스가 **넘어서게 될 때 화면에 어떻게 렌더링할지를 결정**하게 됩니다

     - `auto` 자동 값을 사용할 경우:   
     흐름이 넘치면 x/y 축 모두 스크롤 바가 자동으로 생깁니다.   
     흐름이 넘치지 않으면 스크롤바는 보이지 않습니다.

     - `visible` : 흐름이 넘친 영역이 모두 보여집니다.
     - `hidden` : 흐름이 넘친 영역이 모두 감춰집니다.
     - `scroll` : x/y축 스크롤이 무조건 보입니다.
     - `overflow-x` : x축 방향만 overflow 설정을 수행합니다.
     - `overflow-y` : y축 방향만 overflow 설정을 수행합니다.

## 3day

  ### 질문
  * Q) 요소와 태그는 의미가 같나요?    
       예를들어 `<ol>`요소, `<ol>`태그. 둘 중 어떤식으로 명칭해도 상관없나요? 
  * A) 요소와 태그는 다르다. 그러나 혼용해서 쓰는 경우가 많다. HTML 요소는 여는태그, 속성, 닫는태그 및 스 사이에 있는 모든 것의 모음이다. 반면에 HTML 태그(열림 또는 닫힘)는 요소의 시작 또는 끝을 표시하기 위해 사용된다.     
  그러나 일반적으로 HTML요소와 HTML태그라는 용어는 상호교환이 가능하다.    
  참고 : <https://www.tutorialrepublic.com/html-tutorial/html-elements.php>
    


  ## `<details>` 요소
  - 디스클로저 위젯(disclosure widget, 참고: https://goo.gl/uznvFY)으로 정보를 감추거나, 펼쳐서 보여준다.   
    (보다 자세한 정보를 알려줄 때 사용)
    - 모든 정보를 일시에 공개하지 않고 사용자의 요구에 맞춰 정보를 공개할 수 있다. (화면의 복잡함을 줄임)
    - 아코디언(Accordion) 컴포넌트와 비슷하게 작동한다.
    - 참고로 각주(footnote)에는 적합하지 않다.
      
    * [속성]
        - open - 페이지 로딩 시, 위젯을 펼쳐 표시하도록 설정      
        (open 속성을 사용하지 않을 땐 기본적으로 감춰진 형태로 표시)

       ```html
             [사용 예시]
               <details open>
                 ...
               </details>
       ```
       ```html
           <details open>
            <summary> 사용자와 상호작용하는 요소</summary>
            <p>
              위하여서 풀밭에 청춘의 품고 가치를 그들사막이다. 가치를 넣는 열매를 커다란 방지하는 청춘얼음 부패뿐이다.
            </p>
             </details>
       ```

  ## `<summary>` 요소
   - `<details>` 요소의 레이블/캡션(제목), 서머리(요약) 등을 표시한다.
   - 폼 `<fieldset>` 요소의 제목을 `<legend>`가 표시하듯 비슷하다.

      ```html
      [사용 예시]
        <section class="progress window">
          <h1>"Really Achieving Your Childhood Dreams" 파일 복사</h1>
          <details>
          <summary>복사중... <progress max="375505392" value="97543282"></progress> 25%</summary>
          <dl>
            <dt>초당 전송 속도:</dt>
            <dd>452KB/s</dd>
            <dt>로컬 파일이름:</dt>
            <dd>/home/rpausch/raycd.m4v</dd>
            <dt>원격 파일이름:</dt>
            <dd>/var/www/lectures/raycd.m4v</dd>
            <dt>재생시간:</dt>
            <dd>01:16:27</dd>
            <dt>컬러 프로파일:</dt>
            <dd>SD (6-1-6)</dd>
            <dt>영상 크기(너비×높이):</dt>
            <dd>640×480</dd>
          </dl>
          </details>
        </section>
      ```

  ## `<dialog>` 요소
   - 다이얼로그(Dialog, 참고: https://goo.gl/pQ7gSX)는 사용자의 결정 또는 정보 입력을 요구하는 컴포넌트를 말함.
   - '모달 윈도우'(레이어 팝업) 또는 '대화상자'로도 불린다.

   * [속성]
     - open - 페이지 로딩 시, 위젯을 표시하도록 설정    
        (open 속성을 사용하지 않을 땐 기본적으로 감춰진 형태로 표시)
   * 모든 브라우저가 HTML5.2를 지원하는 것은 아니다. 사용하기 전 확인하기!

        ```html
        [사용 예시]
          <dialog open>
            ...
          </dialog>
        ```
        ```html
        <dialog open>
            <button type="submit">confirm</button>
        </dialog>
        ```


  ---
  #### [참고] 
     더미텍스트 (로렘입숨 Lorem-Ipsum)
      * 콘텐츠와 텍스트가 보이는 상황을 가정해, 임의의 텍스트를 넣어서 폰트나 전체적인 레이아웃을 맞춰볼때 쓰는 용도
        + 영어 <https://www.lipsum.com/>
        + 한글 <http://hangul.thefron.me/>
  ---
  ## `<script>` 요소
   - JavaScript 코드 또는 파일을 HTML 문서에 작성하거나, 연결할 때 사용한다.

      [속성]
        - src
        - type
        - async
        - defer

  ```html
  [코드 예시]
  
    <script src="js/app.js"></script> 

    <script>
      // JavaScript 코드
      console.log('JavaScript 코드를 실행했습니다.');
      console.log(document.characterSet);
      console.log(document.doctype);
    </script>
  ```
  ```html
  <!--외부에 있는 css 파일을 불러올 때 --> <!--`rel` : 현재 서와의 관계-->
    <link rel="stylesheet" href="css/app.css">
    
  <!-- style요소를 직접적으로 html 문서에 작성 할 때 -->
  <style>
    body {
      background-color: #17cc89; 
      margin: 0; 
      min-height: 100vh; 
      width: 100vw;
    }
  </style>

     <!--style요소를 body 부분에 작성할 때-->
     <body style="background-color: #17cc89; margin: 0; min-height: 100vh; width: 100vw;">
    
  <!-- HTML 문서 외부에 있는 JavaScript 파일을 호출하고자  때는 src 속성 사용-->
   <script src="./js/app.js"></script>
  
  <!-- HTML 문서 내부에 JavaScript 코드를 작성할 경우-->
   <script tyep="text/javascript"> (HTML5에서는 타입값을 명시하지 않아도 기본적으로 자바스크립트 코드임을 알고 있기 때문에 생략가능)
     // JavaScript 코드
     console.log('JavaScript 코드를 실행했습니다.');
     console.log(document.characterSet);
     console.log(document.doctype);
   </script>
  ```

  ## `<noscript>` 요소
    - 사용자의 웹 브라우저 환경에서 스크립트를 지원되지 않거나, 스크립트가 꺼져있는 경우, 문서에 표시될 문구를 삽입한다.

   ```html
   [코드 예시]
     <noscript>
       <p>JavaScript를 지원하지 않습니다.</p>
     </noscript>
   ```

  ## `<canvas>` 요소
   - JavaScript를 사용하여 그래픽(비트맵)을 그릴 때 사용한다.     
      `<canvas>` 요소로부터 2D 또는 WebGL 컨텍스트 객체를 추출해 그래픽을 그릴 수 있다.
   - SVG는 확대 했을 때 이미지가 깨지지 않지만 canvas는 이미지가 깨진 그래픽 처럼 보이게 된다.

      [코드 예시]
      ```html
        <canvas width="800" height="600"></canvas>

        <script>
          // canvas 드로잉
          var canvas = document.querySelector('canvas');
          var ctx = canvas.getContext('2d');
          ctx.translate(200, 40);
          ctx.beginPath();
          ctx.moveTo(180, 175);
          ctx.fillStyle = '#ff0';
          ctx.arc(180, 175, 60, Math.PI * -0.35, Math.PI * -1.05, true);
          ctx.fill();
          ctx.beginPath();
          ctx.moveTo(190, 190);
          ctx.fillStyle = '#ff0';
          ctx.arc(190, 190, 100, Math.PI * -0.35, Math.PI * 0.95);
          ctx.fill();
        </script>
      ```
    
## CSS 리스트(Lists) 스타일링

  ### HTML 목록과 관련된 속성
   * HTML 목록 요소 `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>`
      * `<ul>`, `<ol>`, `<li>`
      * `<list-style-type>` : 리스트 타입 선택
          + disc(채워진 원형,ul요소의 기본값) / circle(속이 빈 원형) / square(채워진 사각형)
          + upper-alpha (A,B,C)
          + lower-alpha (a,b,c)
          + decimal (1,2,3) 순자 목록으로 사용 가능
          + decimal-leading-zero (01,02,03)
          + 외국어 등 여러가지 선택가능 

      * `<list-stye-position>` : 리스트 위치(내부, 외부)를 선택
        + outside (기본값) 
        + insid (들여쓰기, 마치 본문처럼 보일 수 있다.)
        + 리스트 여백은 `<ul>`요소의 padding 속성으로 조절할 수 있다. 
  
      * `<list-style-image>` : 기본 리스트 타입대신 이미지를 사용
        + 이미지 주소 url을 입력 
        + url("../image/star.svg")

      * `<list-style>` : 속기 유형 작성법(단축형) **실무에서 많이 사용**
        + square url("star.svg") inside    
      

        [사용 예시]

        ```css
        /*[초기화]*/
        list-style-type: none; (목록 스타일 지우기)
        padding-left: 0; (들여쓰기 X)
        ```
        ```css
         ul{ list-style: none inside url("../images/stat.  svg") }
         /* 또는 */ 
         ul{ list-style: none  url("../images/stat.  svg") }
         /* 또는 */ 
         ul{ list-style:  url("../images/stat.svg") }
        ```
        ```css
        /*margin과 padding*/
        li {
          line-height: 2; 줄 간격
          margin: 10px 0; (배경색이 들어가지 않는다.)
          /* 또는 padding: 10px 0; (배경색이 들어간다.)*/
        }
        ```

  ### HTML 정의 목록 스타일링
    * `<dl>`, `<dt>`, `<dd>`

   ```css
   /*[초기화]*/
   dl {
     margin-top: 0;
     margin-bottom: 0;
   }
   
   dd {
     margin-left: 0;
   }
   ```

  ### HTML 속성을 사용한 순차 목록 출력 설정
   * `<start>`, `<reversed>``<value>` 속성

      ```css
      /*입력한 값부터 순서 시작 (9,10,11,12)*/
      <ol start="9"> 
      
      /*리버스 출력 설정, 반대로 출력 (9,8,7,6)*/
      <ol start="9" reversed>
      /
      
      /*<li>요소에 임의의 숫자값을 입력할 수도 있다.*/
      <li value="20">
      <li value="30">
      <li value="40">
      ```

## CSS 배경 스타일링
  
  ### 배경 색: background-color
   * 배경의 색상을 넣는 속성
   * 속성 값은 rgb() 또는 #으로 시작하는 HEX, 색상 이름 등이 들어 갈 수 있습니다.

     ```css
     iv {
       background-color: #eee;
     }
     ```
    
  ### 배경 위치: background-position
   * background-image의 위치 설정

      * 'left','center','right'로 표현 할 수 있습니다.
      * px이나 %등의 속성이 들어 올 수 있습니다.
      * 값은 x 축 y 축으로 두 개를 띄어쓰기로 구분하여 넣습니다.

      |좌표|값|이동|
      |---|---|---|
      |x|양수, 값 ↑|오른쪽|
      |y|양수, 값 ↑|아래쪽|
      |x|음수, 값 ↓|왼쪽|
      |y|음수, 값 ↓|위쪽|

      ```css
      div {
        background-position: 200px 20px; 

         /* 또는 */
        background-position: 20% 0%; /* x y */

         /* 또는 */
        background-position: left top; /*기본값*/
      }
      ```

  ### 배경 반복: background-repeat
    * background-image의 반복 여부 설정

  ```css
   div {
     background-repeat: repeat; /*기본값*/ 
     background-repeat: no-repeat; /*반복 없음*/
     background-repeat: repeat-y; /*y축으로 배경이미지 반복*/
     background-repeat: repeat-x; /*x축으로 배경이미지 반복*/
   }
  ```

  ### 배경 고정: background-attachment
   * 화면 스크롤이 있을 경우 배경이미지를 고정할 수 있다
   * background-position의 기준 점을 뷰포트(웹 페이지 화면)로 변경할 수 있습니다.
  
      ```css
      div {
        background-attachment : fixed; 
      }
      ```


  ### 배경 크기: background-size
    * 배경 이미지의 크기 설정

  ### background
    * 위에 속성들을 하나로 묶어서 사용

   ```css
     /* transparent는 기본값이기 때문에 안넣어도 상관X */
     div{
       background: 
       transparent 
       url('../img/aa.svg') 
       no-repeat 
       10px 40px 
       fixed;
     }
   ```

  ### 배경 이미지: background-image

   ```css
   .bg-image {
     background: url('../image/aaa.jpg'); no-repaet center center;
     background-size: contain; /*이미지를 모두 박스 안에 포함한다*/
     background-size: cover; /*보여지는 부분은 위치속성으로 설정 가능, 화면 크기에 따라 사진의 크기가 달라지기 때문에 확인하기*/
   }
   ```

  ### 패던(Patterns) 디자인

  ```css
    .is-floral {
      background: #000 url("../images/oriental-floral-pattern.svg");
      background-size: 50px; /* 패턴이미지 크기 조정 */
    }
  ```
  ```css
    .is-model {
      background: url("../images/model.jpg") center;
      background-size: 150px;
    }
  ```

  ### 배경 클리핑: background-clip
   * 배경이미지의 클리핑 영역 설정 content, padding, border
  
  ```css
    .background-clip {
      box-sizing: border-box;
      border: 20px solid rgba(0, 0, 0, 2);
      padding: 20px;
      background: url("../images/model.jpg") center;
      background-size: contain;
      background-clip: content-box; /*클립 속성을 항상 아래쪽에 위치*/
      background-origin: border-box; /*기본값*/
    }
   ```

  ### 배경 기준: background-origin
   * 배경이미지의 시작에 대한 기준점 설정 content, padding, border

---
# 4day

  ## 플로팅(Floating) 레이아웃
   * 일반적인 레이아웃 흐름(Normal Layout Flow)
     + HTML이 기본적으로 화면에 렌더링하는 것을 말함. 마크업 순서대로 위에서 부터 아래 방향으로 나열(CSS 미반영)

   * 플로팅 레이아웃(Floating)
   * float 속성을 사용해 박스를 왼쪽(left) 또는 오른쪽(right)으로 **"부유"**시키는 레이아웃 기법.

  ### [`<float>` 속성]
   * 속성 : `<none>`(기본값), `<left>`, `<right>`

      ```css
      /* 부모요소는 float으로만 구성된 자식요소를 감싸지 못함*/
      /* Clearfix, 가상요소를 사용해서 문제 해결가능*/
      .box.is-blue {
        float: left;
        width: 200px;
      }
      .box.is-yellow {
        float: left;
      }
      .box.is-green {
        float: left;
      }

      .clear {
        clear: both;
      }
      ```
      ```html
      <!-- 이해를 돕기위한 코드 많이 사용하지 X -->
        <div class="box-group">
          <div class="box is-blue"></div>
          <div class="box is-yellow"></div>
          <div class="box is-green"></div>
          <div class="clear"></div>
        </div>
      </section>
      ```

  ### [`<clear>` 속성]
    
   + float를 해제시키는 속성 (부모요소가 자식을 감쌀 수 있게 함)

  ```css
    .clear {
      clear: none; /**/
      clear: left; /* float: left 해지 */
      clear: right; /*  */
      clear: both; /* 주로 많이 씀 */
    }
  ```

  ### 가상 요소 `<::after>` 사용
   * 참고 : <https://takeuu.tistory.com/60>
    
      ```css
      .clearfix::after {
        content: '';
        display: block;
        clear: both;
        visibility: hidden;
      }
      ```

  ## 유저 인터렉션 속성
  
   ### `<hidden>` 속성

   - 모든 HTML 요소들은 hidden 속성을 가질 수 있으며, 요소에 설정되면 요소가아직 페이지의 현재 상태와 직접적으로 관련이 없거나 페이지의 다른 부분에서 내용을 재사용하도록 선언하는 데 사용된다. 브라우저는 hidden 속성이 설정된 요소를 화면에 렌더링하지 않는다.
      
        ```html
        [사용 예시]
          <div class="container">
  
          <img
            class="drag-element"
            src="images/fashion-model-pose.png"
            alt="패션 모델"
            width="276" height="417">
  
            <div class="dropzone">
              <p>Drop Zone</p>
            </div>
          </div>
        ```

   ### tabindex 속성
   - 요소를 키보드로 탐색할 수 있도록 설정하거나, 제외 또는 순서대로 탐색할 수 있도록 설정할 수 있다. 
   - **"탭(Tab) 이동"**이란 용어는 순차적 포커스 탐색을 사용하여 포커스 가능(Focusable) 요소 사이를 이동하는 것을 의미한다.

   - [기본적으로 포커스 가능한 요소들](참고: https://allyjs.io/data-tables/focusable.html)
     - 폼 컨트롤 요소들           : input, button, textarea, select 등
     - href 속성을 가진 요소들     : a, area
     - controls 속성을 가진 요소들 : video, audio

         ```html
        [사용 예시]
          // [양수] 탭 포커스 순서(2번째)를 설정한다.
          // (논리적 포커스 흐름에 방해가 되기에 사용을 권장하지 않음)
          // button요소는 기본적으로 Tab이 발생 됨 
          <button 
            type="button"
            class="button is-play"
            tabindex="2">재생</button>

          // [0] div 요소는 포커스를 가지지 않는 요소이지만, 포커스를 적용할 수 있게 된다.
          // 컴포넌트 제작 시, 비 포커스 요소에 포커스를 적용해야 할 경우 유용하게 사용됨.
          <div tabindex="0"></div>

          // [-1] 일반적인 포커스 순서에서 제외시킬 수 있다.
          // (JavaScript 프로그래밍으로 포커스 처리 가능)
          // 컴포넌트의 일부 요소를 일시적으로 포커스 순서에서 제외한 후,
          // 목표에 따라 포커스를 다시 활성화 처리할 수 있다.
          // <a>요소는 기본적으로 포커스를 가지고 있다.
          <ol class="TOC">
            <li><a href="#pinch">위기</a></li>
            <li><a href="#overcome" tabindex="-1">극복</a></li>
          </ol>
          ```


   ### accesskey 속성
   - 모든 HTML 요소는 accesskey 속성을 가질 수있다. 속성 값은 키보드 단축키로 설정된다.
   - 하지만 accesskey 속성의 단축키는 브라우저와 운영체제 플랫폼에 의존하고 있어 운영체제마다 사용자 경험이 달라진다. 쉽게 말해 Windows 사용자와 Mac OSX 사용자가 사용하는 단축키는 달라진다. (iPhone과 Android 사용자 경험이 다른 것처럼)

        
        ```
        [브라우저 × 운영체제 플랫폼]
          Windows
            Chrome  : Alt + 단축키
            IE      : Alt + 단축키
            Safari  : Alt + 단축키
            Opera   : Alt + 단축키
            Firefox : Alt + Shift + 단축키
          Mac OSX
            Chrome  : Control + Alt + 단축키
            Safari  : Control + Alt + 단축키
            Opera   : Control + Alt + 단축키
            Firefox : Control + 단축키
          Linux
            Chrome  : Alt + 단축키
            Opera   : Alt + 단축키
            Firefox : Alt + Shift + 단축키
        ```

        ```html
        [사용 예시]
          <button
            type="button"
            class="button is-collect"
            accesskey="C"
            onclick="collect()">
            수집
          </button>
        ```


   ### contenteditable 속성
   - contenteditable 속성이 설정된 요소는 사용자가 직접 편집할 수 있도록 만들어 준다.
        + 값이 true 또는 빈 문자열("")일 경우 편집 허용.
        + 값이 false 일 경우 편집을 허용하지 않음.
      ```html
        [사용 예시]
        <p contenteditable>
          ...
        </p>
        ```


   ### draggable 속성
   - 모든 HTML 요소는 draggable 속성을 가질 수 있다.
      + 값이 true 일 경우 드래그(Drag) 가능.
      + 값이 false 또는 빈 문자열("")일 경우 드래그 불가능.
   - 마우스에 의존하기 때문에 마우스를 사용하지 못하는 사용자에게 불편하다.
        ```html
        [사용 예시]
        <p draggable="true">
          ...
        </p>
        ```

   ### 좋은 프론트엔드 개발자의 자격 요건
   * 프론트엔드 개발자는 모든 사용자를 고려하는 설계자가 되야 한다. 
   * 구조를 탄탄하고 의미적으로 구성할 수 있어야 한다.
   * 디자이너가 만든 비주얼을 화면에 구성할 수 있는 표현 능력이 가능해야 한다. (CSS)
   * 사회적 약자 계층도 이용할 수 있도록 서비스를 만들어야 한다. 







