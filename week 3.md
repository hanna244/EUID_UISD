# EUID_UISD

# 1day


## 2D 트랜스폼

  * 2D 트랜스폼(Transform)
  
     + 회전
      - rotateX(angle)
      - rotateY(angle)
      - rotate(angle)
     + 크기
      - scaleX()  // **scalex(1) = 1 값은 100%를 의미** 
      - scaleY()
      - scale(x, y) (X, Y 동시에 적용)
      - scale() (X, Y 동시에 같은 값을 적용) 
     + 이동
      - translateX()
      - translateY()
      - translate(x, y) (X, Y 동시에 적용)
     + 비틈
      - skewX()
      - skewY()
      - skew(x, y)

  ```css
    /* 회전 */
    .headline {
      transform: rotateX(30deg);
      transform: rotateY(60deg); 
      transform: rotate(90deg); 
      transform: rotate(1.2turn); 
    }
    
    /* 크기 */
    .headline {
      transform: scaleX(1.5); (너비를 잡아 당기다)
      transform: scaleX(1.5) scaleY(0.7); (너비를 당기고 길이를 줄이다.)
      transform: scale(1.5, 0.7); 
      transform: scale(1.5); 
    }
    
    /* 이동 */
    .headline {
      transform: translateX(-40px) translateY(-140px) rotate(10deg); 
      transform: translate(120px -40px) 
    }
    
    /* 비틈 */
    .headline {
      transform: skewX(30deg);
    }
    
    /* 이미지의 회전축 */
    .headline {
      transform-origin: 50% 50% (x, y 기본값)
      transform: rotate(70deg);
    }
  ```
  [주의]
  ```css
      .headline {
      transform: scaleX(0.5);
      transform: scaleY(0.5); /* 아래에 있는 y값이 위의 x값을 덮어쓰게 된다. */
      /* transform: scale(0.5,0.5); */
      /* transform: scaleX(0.5) scaleY(0.5) */
      }
  ```
  * 한 요소에 여러개의 `<transform>`을 사용할 때는 확인

## 트랜지션 (Transitions)
  * CSS 트랜지션은 CSS 속성을 변경할 때 애니메이션 속도를 조절하는 방법을 제공합니다.

  * [참고]
    + CSS 트랜지션 사용하기 : <https://developer.mozilla.org/ko/docs/Web/CSS/CSS_Transitions/Using_CSS_transitions>

  * CSS 트랜지션(Transition): IE 10+

    + `transition-property`         트랜지션 속성
      - `<all>`(기본값)
    + `transition-duration`         트랜지션 시간
      - 변화가 일어나는 기간(1.2s, 4s), 초단위, (기본값 0s)
    + `transition-timing-function`  트랜지션 타이밍 함수

      - 트렌지션 효과가 진행하는 동안 속도의 변화를 지정    
        - ease : 기본값, 천천히 시작해서, 빠르게 진행하며, 천천히 끝남. 
          + cubic-bezier(0.25,0.1,0.25,1)
        - linear : 처음과 끝이 같은 속도로 나타남
          + cubic-bezier(0,0,1,1)
        - ease-in : 천천히 시작
          + cubic-bezier(0.42,0,1,1)
        - ease-uot  : 천천히 끝남
          + cubic-bezier(0,0,0.58,1)
        - ease-in-out : 천천히 시작해서 천천히 끝남
          + cubic-bezier(0.42,0,0.58,1)
        - cubic-bezier(n,n,n,n) : 직접 값을 지정할 수 있음. 가능한 값은 0부터 1까지 숫자값
          - easings.net : <https://easings.net/ko>
          - Ceaser - CSS EASING ANIMATION TOOL : <https://matthewlein.com/tools/ceaser>
      - ```css
          /* 임의 값 */
          transition-timing-function: cubic-bezier(0.085, 1.350, 0.930, -0.565);

          /* CSS 기본 설정 가능한 값 */
          transition-timing-function: linear;
        ```

    + `transition-delay`            트랜지션 지연시간
      - 트랜지션 효과가 시작되기 전 기다리는 시간
    + `transition`                  트랜지션 속기형

      - transition: `<prop>` `<dur>` `<timfn>` `<delay>`
      ```css
      .headline {
          transition: top 0.4s ease, transform 0.6s ease-in-out 0.4s;

          /* 또는 */
          transition: all 0.4s ease-out 0.32s;
      }
      ```
    
    ```css
    .headline {
          /* 초기 상태(initial state) */
      position: absolute;
      top: 100px;
      left: 40%;
      margin-left: -156px;
      transition-property: top, transform; /*또는 all*/
      transition-duration: 0.45s 0.8s;
      transition-timing-function: linear;
      transition-delay: 0.4s, 0.4s;
    }
    
      .headline:hover {
          /* 종료 상태 (final state) */
          top: 100px;
          transform: rotate(10deg);
      }
    ```

## 3D 트랜스폼 (Transforms)

  * <트랜스폼을 적용할 요소에 적용 하는 속성>
   
    * transform-origin 회전을 시킬 축을 결정
      + 기본값 (50% 50%)
      + (0% 0%)일 때 이미지 위의 왼쪽 끝이 회전축이 된다.
    * backface-visibility
   
    * rotateX()
    * rotateY()
    * rotateZ() = rotate()
    * rotate3d(x, y, z)
   
    * translateX()
    * translateY()
    * translateZ() = translate()
    * translate3d(x, y, z)

    * scaleX()
    * scaleY()
    * scaleZ() = scale()
    * scale3d(x, y, z)

    * skewX() 
    * skewY()
    * skew()
      - skew는 skewZ()인 Z축이 없으며 사실 3D가 아니다.

   * perspective() 투시도법 (원근법에 따라 눈에 보이는 그대로 그리는 기법)
     + 값이 커질 수록 왜곡이 작아진다.
     + 예를 들어, 건축도면 등에서 투시도법을 많이 사용

   * <자식 요소를 3D 처리할 부모 요소에 설정>

   * perspective 
   * perspective-origin (원근법의 기준점을 설정)
   * **transform-style: preserve-3d** (요소의 자식이 3D 공간에 배치)


  * [참고]
    + `<backface-visibility>` : 요소의 뒷면이 사용자를 향할 때 보여야 하는지 지정합니다.
      ```css
      .album-player {
      backface-visibility: visible;
      backface-visibility: hidden;
      }
      ```
  
  ```html
  <ul class="album-list">
    <li class="album-card">
      <img
        class="album-cover">
      <iframe class="album-player" src="//goo.gl/syBGn1"></iframe>
    </li>
  </ul>
  ```
  ```css
    /*  ---앨범 카드---  */
  .album-card {
    cursor: pointer;
    float: left;
    width: 340px;
    height: 340px;
    margin: 30px;
    transition: box-shadow 0.3s ease-in-out;
  }
  
  .album-card:hover {
    box-shadow: 0 0 0 1px #ff6a03, 0 0 40px 5px hsla(25, 100%, 51%, 0.3);
  }
  
  .album-card * {
    position: relative;
    top: 0;
    left: 0;
    width: inherit;
    height: inherit;
    transition: all 0.8s cubic-bezier(0.230, 1.000, 0.320, 1.000) 0.5s;
    transform-style: preserve-3d;  
  }

  .album-card:hover .album-cover {
      transform: perspective(1000px) rotate(180deg) scale(0.5);
  }

  .album-card:hover .album-player {
    transform: perspective(1000px) rotate(360deg) scale(0.5);
   /* perspective(1000px) 값은 부모요소에 일괄적용 하면 상속된다. */

  
  /* ---앨범 커버--- */ 
  .album-cover {
    transform: perspective(400px) rotate(45deg);
  }
  
  
  /* ---앨범 플레이어---  */
  .album-player {
    border: none;
    transform: rotate(180deg);
    backface-visibility: hidden; 
    /* 해당 요소를 적용시키기 위해서는 부모요소에게  
    transform-style: preserve-3d;를 적용시켜 
    자식들이 3D공간에 있다는 것을 알려주어야 한다. */
  }
  ```
---
# 2day

### 질문
  * CSS
    - Q1) 애니메이션 속기형을 입력할 때 속성을 입력하는 순서는  상관 없나요?    


## CSS - 애니메이션 

  * 애니메이션(Animation)
  
    + `animation-name`              애니메이션 이름 (@keyframes 이름)
    + `animation-duration`          애니메이션 시간(초단위)
    + `animation-timing-function`   애니메이션 타이밍 함수
    + `animation-delay`             애니메이션 지연시간

       - 400ms(= 0.4s), 2s, -2s
       - 음수 값을 지정하면 애니메이션이 즉시 시작되지만 애니메이션 주기의 도중에 시작된다.

    + `animation-direction`         애니메이션 종료 후, 진행 (순/역)방향

       - `<normal>`            : from - to (기본값)
       - `<reverse>`           : to - from
       - `<alternate>`         : 홀(nomal) 짝(reverse)
       - `<alternate-reverse>` : 홀(reverse) 짝(nomal)

    + `animation-iteration-count`   애니메이션 반복 횟수 

      - 1(기본값), `<number>`(2,4,1.5...), `<infinite>`무한반복

    + `animation-play-state`        애니메이션 재생/일시정지 설정
       - `<running>`(기본값) `<paused>` 
    + `animation-fill-mode`         애니메이션 시작 전/종료 후 키프레임 설정 
    애니메이션이 실행 상태가 아닐 때 (대기 or 종료) 요소의 스타일 지정

        - `<none>`:       
          - 대기 -> 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
          - 종료 -> 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.

        - `<forwards>`:   
          - 대기 -> 시작 프레임(from)에 설정한 스타일을 적용하지 않고 대기한다.
          - 종료 -> 종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.

        - `<backwrads>`:  
          - 대기 -> 시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
          - 종료 -> 애니메이션 실행 전 상태로 애니메이션 요소의 프로퍼티값을 되돌리고 종료한다.

        - `<both>` :      
          - 대기 -> 시작 프레임(from)에 설정한 스타일을 적용하고 대기한다.
          - 종료 -> 종료 프레임(to)에 설정한 스타일을 적용하고 종료한다.

    + `animation`                   애니메이션 속기형
      - 순서 : `<name>` `<timing-funtion>` `<iterration-count>` `<direction>` `<fill-mode>` `<delay> `<play-state>`
  
    ```css
      .sonic {
        animation-name: sonic-running;
      }
    
      /* 애니메이션 정의 */
      @keyframes sonic-running { /* @keyframes 이름 */
        from {}                  /* 시작하는 지점의 상태, 생략 가능 */
        to {}                    /* 끝나는 지점의 상태 */
        
      }
    
      /* 또는 */
      @keyframes sonic-running {
        0% {} /* from {} */
        50% {}  
        75% {}  
        100% {}  /* to {} */
      }
    ```
  * [`animation-play-state`]
  ```css
      .sonic {
      animation-play-state: paused
    }

    /* 응용 */
    .sonic-sonic-adventure:active .sonic {
      animation-play-state: paused;   /* 클릭 시 멈춤 */
      animation-play-state: running;  /* 클릭 시 재생 */
    }
  ```

## HTML - 테이블 요소

  `<table>` 요소
  - 테이블 **몸체**에 해당되며, 행(row)/열(column) 및 셀(cell)을 포함한다.
    복잡한 내용을 x, y축에 따라 이해하기 쉽게 데이터를 구조화하는데 테이블을 사용한다.   
    가장 좋은 테이블 디자인은 최대한 단순하게 표를 구성하는 것이다.   
    테이블 내 테이블을 중첩해서는 안된다.   
    테이블을 레이아웃(배치) 목적으로 사용해서는 안된다.   
    border 속성을 사용해 테두리를 그릴 수 있다. (CSS로 대체하는 것이 좋다)

  `<caption>` 요소
  - 테이블의 **제목**을 명시적으로 제공하며, 제작자는 표의 내용을 이해할 수 있도록 정보를 제공해야 함.   
    테이블 내용이 복잡해 설명이 필요하다면 아래 나열된 방법 중 하나를 선택해 기술해야 한다.

    * [설명(summary)을 추가하는 방법]
        1. aria-describedby 속성을 사용해 설명 단락(paragraph)을 연결
        2. `<figure>` 요소에 aria-labelledby 속성을 사용해 제목(caption)을 연결

  ```hrml
  <p id="compare-shoes-table">국제(한국, 영궁, 유럽) 성인 남성 운동화 사이즈 비교 표로 4행 12열로 구성되어 있습니다.</p>
  <table border="1" aria-describedby="compare-shoes-table">
  ```

  + `<tr>` 요소
    - 테이블의 **행(row)**을 말하며 내부에 셀 제목(header), 셀 내용(data)을 포함한다.
      
  + `<th>` 요소
    - 테이블 셀 **제목(header cell in a table)**으로 **행(tr) 내부에 포함되어야 한다.**

    * [속성]   
          **`<scope>`**: 행(row) 또는 열(col), 행그룹(rowgroup), 열그룹(colgroup)의 **제목임을 명시**   
          `<abbr>`: 제목이 길어 축약(Abbreviation)이 필요할 때 사용   
          `<colspan>`: 열(column)을 그룹 지을 때(병합) 사용   
          `<rowspan>`: 행(row)을 그룹 지을 때(병합) 사용

  ```html
  <th scope="row">한국(mm)</th>
  ``` 


  + `<td>` 요소
    - 테이블 셀 **내용(data cell in a table)**으로 **행(tr) 내부에 포함되어야 한다.**

      * [속성]   
          `<colspan>`: 열(column)을 그룹 지을 때 사용   
          `<rowspan>`: 행(row)을 그룹 지을 때 사용   
          `<headers>`: 셀 제목을 하나 이상 연결하여 읽기 용이하도록 구성할 때 사용
  ```html
  <thead>
  <tr>
    <th id="rd-1" scope="col" rowspan="2">공급/전용(㎡)</th>
    <th id="rd-2" scope="colgroup" colspan="3">매매 실거래가(만원)</th>
  </tr>
  <tr>
    <th id="rd-2-1" scope="col">최저가(㎡)</th>
  </tr>
  </thead>
  <tfoot>
  <tr>
    <td>84/59.99</td>
    <td headers="rd-1 rd-2 rd-2-1">47,800(4층)</td>
  </tr>
  </tfoot>
  ```

  * `<thead>` 요소
    - 테이블 행 블록(row block) 내에 **제목 열 그룹(column headers)으로 구성할 경우** 사용한다.
        선택적(option)으로 사용한다. (필수 아님)

  * `<tbody>` 요소
    - 행 블록 내에 **테이블 데이터로 구성할 때** 사용한다.
        선택적(option)으로 사용한다. (필수 아님)

  * `<tfoot>` 요소
    - 행 블록 내에 열 요약(column summaries)로 구성할 때 사용한다.
        선택적(option)으로 사용한다. (필수 아님)

  * `<col>` 요소
    - 테이블 **열(column)을 하나 이상 묶고자 할 때** 사용한다.
        일반적으로 `<colgroup>` 요소 내부에 포함시킨다.
        선택적(option)으로 사용한다. (필수 아님)

      * [속성]   
        `<span>`: 열 묶음 개수 설정

  * `<colgroup>` 요소
    - 테이블 열(column) 그룹을 만들고자 할 때 사용한다.
        **내부에 col 요소를 포함하거나, 포함하지 않을 수 있다.**
        선택적(option)으로 사용한다. (필수 아님)

      * [속성]   
        `<span>`: colgroup 요소가 col을 포함하지 않을 경우, 열 묶음 개수 설정

---
# 3day

## CSS - 그레디언트

  * [기본 문법]
    - 첫 시작(0%)과 끝(100%)의 퍼센트는 입력하지 않아도 적용 가능
    ```css
      body {
        background: linear-gradient(
          각도,      /* 또는 방향(목적지) */
          시작 색상, 
          끝 색상    /* 중간색상 추가 가능 */
          ); 
      }
    ```

### 선형 그레디언트 

  * 적용
    ```css
      body {
        background: linear-gradient(90deg, #0e0f12, #f7e763);
      
      /* 
      90deg  : to right
      180deg : to bottom
      0deg   : to top
      45deg  : to top right
      -45deg : to top left 
      */ 

      /* [색상을 선명하게 구문지어 주고 싶다면] */

        background: linear-gradient(   
          45deg, 
          #ff3400 40%,
          #45d5bf 40%,
          #45d5bf 60%,
          #3a2c76 60%,
          #3a2c76
          );
      }
    ```

### 원형 그레디언트
  * 원 모양의 값 (화면 폭에 따라 원의 모양, 크기가 달라짐)
    + `circle`  정원형 
    + `ellipse` 기본값(생략 가능)
  * `farthest-side` 기본값    
  `closest-side` 정원형의 크기와 비슷하게 그라데이션이 나타남
  ```css
    body {
      background: radial-gradient(
        #6c52da
        #3a2c76
        );
    
      background: radial-gradient(
        circle closest-side,
        #6c52da 25%,
        #45d5bf 25%,
        #45d5bf 50%,
        #3a2c76 50%
        );
    }
  ```
  
### 배경 패턴 
  ```css
    body{ 
      background: url("//goo.gl/B6SfbX");
      background-size: 90px; 
     /* 사이즈를 설정해서 이미지의 크기를 조정하면 패턴 형태로 나타남 */
  }  
  ```
  
  * [오버레이 그레디언트]   
    + 멀티 배경 테크닉 활용
      - 마크업 순서에 따라 배경 위로 올라옴
    
      ```css
        body{ 
          background: 
          /* linear-gradient(45deg, #45d5bf, #3a2c76) 투명도가 조정되지 않았기 때문에 아래의 이미지가 보이지 않음*/
            linear-gradient(
              45deg, 
              hsla(12, 100%, 50%, 0.2), 
              hsla(54, 90%, 68%, 0.2)),
            url("//goo.gl/B6SfbX");
          background-size: contain, 120px;
        }  
      ```
  
### 멀티 그레디언트 
  ```css
  body{ 
   background: 
    linear-gradient(217deg, rgba(255,0,0,0.45), rgba(255,0,0,0) 65.70%),
    linear-gradient(127deg, rgba(0,255,0,0.45), rgba(0,255,0,0) 65.70%),
    linear-gradient(336deg, rgba(0,0,255,0.45), rgba(0,0,255,0) 65.70%),
    url("//goo.gl/B6SfbX");
  background-size: 100%, 100%, 100%, 140px; 
    
  background: 
    /* 'circle at 50% 0'(x, y) 원이 뿌려져 나가는 위치 설정 가능 */
    radial-gradient(circle at 50% 0, rgba(255,0,0,0.45), rgba(255,0,0,0) 65.70%),
    radial-gradient(circle at 6.7% 75%, rgba(0,255,0,0.45), rgba(0,255,0,0) 65.70%),
    radial-gradient(circle at 93.3% 75%, rgba(0,0,255,0.45), rgba(0,0,255,0) 65.70%),
    url("//goo.gl/B6SfbX");
  background-size: 100%, 100%, 100%, 140px; 
  }  
  ```
  
### 반복 그레디언트 

  ```css
  body {
    /* [선형 그레디언트] */
    background: repeating-linear-gradient(
      45deg,
      #ff3400,
      #ff3400 10px,
      #45d5bf 10px,
      #45d5bf 20px
    );

    /* [원형 그레디언트] */
    background: repeating-radial-gradient(
      circle at 50% 15%,
      #ff3400,
      #ff3400 10px,
      #45d5bf 10px,
      #45d5bf 20px
    );
  }
  ```

### 박스 그림자

  * 기본 문법
    ```css
      header {
        box-shadow: x y blur spread(사이즈) color; 
        /* 또는 x y blur color */
      }
    ```

  * 박스 그림자
    + 박스 그림자의 x y를 0으로 설정하면 박스 사방으로 그림자가 나타나는 형태가 된다. 이를 이용해서 `<border>`와 같이 이미지의 테두리를 설정해 줄 수 있다. 
    ```css
    header {
        /* 박스 그림자 ------ */
    box-shadow: 0 6px 15px rgba(0,0,0,0.35); 

        /* 박스 안쪽 그림자 ------ */
    box-shadow: inset 0 -5px 15px 4px rgba(0,0,0,0.35); 

        /* 박스 그림자 설정 ------ */
    box-shadow: 0 0 0 1px #3f3f3f; 

        /* 둥근 테두리 설정 ------ */
        /* 순서 : 왼쪽상단 오른쪽상단 오른쪽하단 왼쪽하단 */
    border-radius: 170px 0 0 170px; 
    }
    ```

### 멀티 박스 그림자 설정
  ```css
  .album-card:hover {
    transform: scale(1.05); 
  
    box-shadow: 
      0 25px 20px -20px rgba(0,0,0,0.25),
      0 3px 15px rgba(0,0,0,0.5);
  }
  ```
### 광택(glossy) 효과 설정
  ```html
  <ul class="album-list">
    <li class="album-card has-gossy"></li>
  </ul>
  ```
  ```css
  .album-card.has-glossy::before {
    background: 
      linear-gradient(
        148deg, 
        rgba(255,255,255,0) 20%,
        rgba(255,255,255,0.15) 47%, 
        rgba(255,255,255,0.3) 47%, 
        rgba(255,255,255,0.3) 47.1%, 
        transparent 47.1%
        );
  }
  ```

---
# 4day

## 질문 

  * Q1) border-image-slice의 값을 퍼센트로 지정할 때, 퍼센트는 X, Y축 값을 사용하는 건가요? 

  * Q2) '버튼 폼 컨트롤로 사용자의 인터랙션을 받아 액션을 트리깅(방아쇠) 처리함.'이라는 말은 '사용자가 버튼을 클릭 했을 때 브라우저가 실행된다'라는 말과 같나요?
  '트리깅 처리'라는 것이 잘 이해가 안됩니다. '브라우저 실행'이 맞나요?

  * Q3)
      ```html
      <fieldset name="user_account">
        <legend>사용자 계정</legend>
      </fieldset>
      ```
      `<fieldset>`요소의 이름의 값인 '사용자 계정'은 개발자가 구분을 편하게 하기 위해 입력한 이름이고,    
      `<legend>`의 '사용자 계정'은 브라우저에서 사용자에게 보여주는 이름인가요?    
      또한 `<fieldset>`의 이름은 꼭 설정하지 않아도 되는 건가요? 

## 보더 이미지 (Border Image)



  * [문법]

    **border-image: source [slice / width / outset repeat]** 속기형으로 자주 씀

    border-image-source 필수로 입력   
    border-image-slice   
    border-image-width   
    border-image-outset   
    border-image-repeat   


  * [source] : url() 함수를 사용하여 이미지 경로를 설정합니다.


  * [slice / width / outset]

    - slice
      슬라이스는 이미지의 상(⬆︎), 우(➡︎), 하(⬇︎), 좌(⬅︎) 가장자리 오프셋을 설정합니다. (최대 4개)
      보더 이미지를 9개 영역으로 나눌(slice) 수 있습니다. (px 단위 사용 X)
      - Ex) 슬라이스를 10px로 설정한다. (border-image-slice: 10px;)
        + 이미지를 9개의 영역으로 나누었을 때, 꼭지점 영역에 해당하는 부분의 이미지를 상하좌우 10px에 해당하는 부분만큼 잘라서 사용한다. 
      
      ```css
          /* 위 아래 이미지의 길이가 안맞으면... 사다리꼴 모양이 되는 건가...? 
          상하, 좌우 단위를 통일? 보더 다시 한 번 보기 */

      div {
        border: 10px solid #ddd;
        border-image: url();
        border-image-slice: 30;         /* 모든 방향 */
        border-image-slice: 10% 30%;    /* 세로 가로 */
        border-image-slice: 30 10% 45;  /* 위 가로 세로 */
        border-image-slice: 10 15 10 20;/* 위 오른쪽 아래 왼쪽 (시계방향) */
        
        /* fill 키워드는 선택한 이미지를 박스 안의 배경이미지로 사용,
        입력 순서 상관없이 아무데나 키워드 추가 가능*/
        border-image-slice: 10% flii 30%;
      }

    - width
      - 요소의 상/우/하/좌 테두리 이미지 너비(width)를 설정합니다. (최대 4개)   
      실제 테두리의 너비는 영향을 받지 않고 이미지는 맨 위에 배치됩니다.    
      border-image 너비가 border-width 보다 클 경우 채우기 영역 또는 내용 영역을 포함합니다.    
      **단위 없는 값**은 요소의 테두리 너비의 배수로 해석됩니다.    
      테두리 이미지 너비는 기본적으로 테두리 너비와 같습니다.

    - outset (테두리와 콘텐츠 사이 안쪽 여백 크기 조정)
      - 테두리 이미지를 주어진 값만큼 패딩(안쪽) 영역을 설정합니다. (최대 4개)     
      단위 없는 값을 사용할 경우, 요소의 테두리 너비(width)에 곱하여 오프셋합니다.


 * [repeat 설정]
    - stretch : 기본값, 이미지를 늘린다.
    - repeat  : 이미지를 반복. 단, 반복되는 이미지의 사이즈가 가로, 세로 길이에 딱 맞지 않아 남거나 모자랄 경우 부자연스럽게 이미지가 잘린다.
    - round   : 이미지를 반복. 크기가 안맞을 경우 이미지를 늘리거나 줄여서 자연스럽게 연결되게 함.
    - space   : 이미지를 반복. 크기가 안맞을 경우 공백 처리.


  * [예시]
```
  // 슬라이스 10px 설정, 나머지(width / outset)은 기본값 사용, 가장자리 섹션 stretch 사용
  border-image: url('imageUrl') 10;

  // 각 테두리 방향에서 5% 조각 이미지 사용, 가장자리 반복 설정
  border-image: url('imageUrl') 5% round;

  // 슬라이스 오프셋 ⇒ 순서: 위 오른쪽 아래 왼쪽
  border-image: url('imageUrl') 10 20 30 40;

  // 슬라이스 10px 설정, 테두리를 2배 큰 border-width 값으로 크기 조정, 가장자리 반복 설정
  border-image: url('imageUrl') 10 / 2 repeat;

     /* border-image: url('imageUrl') 10 repeat;
     border-image-width: 2; */

  // 테두리를 2배 큰 border-width 값으로 크기 조정하고 
  // 여백 테두리는 1배 border-width 값으로 설정
  border-image: url('imageUrl') 5 / 2 / 1;

  // 4개의 가장자리마다 각기 다른 설정
  border-image: url('imageUrl') 5 8 6 10 / 1 2 1 3 / 0 1 .5 .5;
```

* [그레디언트 보더 이미지]

  ```html
  <figure>
  <figcaption>CSS 그레디언트 보더 이미지</figcaption>
    <div class="is-gradient">
      <img class="is-rwd" src="//images.unsplash.com/" alt>
    </div>
  </figure>
  ```
  ```css
  .is-gradient {
  width: 50vw;
  border: 20px solid #f98b14;
	border-image: linear-gradient(-45deg, #00b9e9, #f98b14, #503370) 20;
  }
  ```

## 폼 디자인

  * `<form>`
    - 폼은 텍스트필드, 버튼, 체크박스와 같은 폼 컨트롤을 포함하는 웹 페이지의 컴포넌트를 말함.
      + 사용자와 인터랙션을 수행한 결과(예: 검색)를 서버로 보낼 수 있다.
      - 즉, 사용자가 폼에 입력한 정보를 입력하고 폼 컨트롤을 클릭했을 때, 실행되는 브라우저에 입력한 정보를 전송하는 것이다.??

      [사용 예시]
    ```html
      <body>
        <form action="https://formspree.io/your@email.com" method="POST">
          <input type="text">
        </form>
      </body>
    ```

  * `<method>`
    - `<GET>` 
      + 기본값, 폼에 입력한 사용자의 정보가 url에 그대로 나타남
      + 일반적으로 많이 사용
    - `<POST>`
      + 폼에 입력한 사용자의 정보가 숨겨짐 
      + 민감한 정보 데이터를 전송할 때 사용 (사용자의 로그인 정보 등)

  * `<input>`
    - 사용자의 데이터를 입력 받을 수 있는 폼 컨트롤을 말함.
      다양한 유형(Type) 설정이 가능하며, 유형에 맞는 역할을 수행한다.
    - 닫는 태그가 없음.

      [속성]
        - name : 서버의 이름
        - placeholder : 사용자에게 무엇을 입력해야 할지 도움을 준다. 
        - value
        - readonly : 읽기만 가능 사용자가 입력할 수 없음(value 값 설정 가능)
        - required : 필수 입력사항, 입력하지 않을 시에 전송 불가
        - disabled : 비활성화
        - minlength : 최소 입력 글자 수 설정
        - maxlength : 최대 입력 글자 수 설정
        - list

      [유형]
        - text : 텍스트를 입력할 수 있는 사각형 박스 생성
        - password : 텍스트 입력 시에 ...과 같은 형태로 입력됨
        - checkbox : 
        - radio : 
        - file : 파일을 전송할 때 사용 (form 요소에 'enctype="multipart-formdata"와 method 방식은 POST로 반드시 입력해야 함)
        - submit 
        - button 
        - image
        - reset 
        - hidden : 사용자에게 보여지지 않으며 데이터를 전송할 때 사용 
        - search
        - url
        - tel
        - email
        - date
        - month
        - week
        - time
        - datetime-local
        - number
        - range
        - color


      [사용 예시]
      ```html
        <body>
          <input type="text">
          <input type="submit" value="전송">
          <input type="button" value="버튼">
          <input type="image" src="https://goo.gl/Ng66oQ" alt="체크인" width="20" height="20">
          <input type="reset" value="초기화">
          <input type="hidden" name="using-ajax" value="true">
          <input type="number" name="" id="" min="100" step="10" max="1000" value="150">
          <input type="range" name="" id="" min="10" step="5" max="25" value="15">
          <input type="color" name="" id="" value="#F7CC60">
        </body>
      ```

  * `<checkbox>` 
    - 여러 선택지 중에 **중복**해서 선택할 때 사용
  * `<radio>` 
    - 여러 선택지 중에 **한 개**를 선택할 때 사용
    - 주의) `name`값이 반드시 **같아야** 한다.  
    같지 않을 경우 값이 다른 것과 중복 선택이 가능해진다.

    ```html
      <body>
        <!-- checkbox -->
        <p>
          <label><input type="checkbox" name="number" velue="one" checked>1</label>
          <label><input type="checkbox" name="number" velue="two" checked>2</label>
          <label><input type="checkbox" name="number" velue="three">3</label>
        </p>

        <!-- radio -->
        <p>
          <label><input type="radio" name="color" value="red">빨강</label>
          <label><input type="radio" name="color" value="black" checked>검정</label>
          <label><input type="radio" name="color" value="blue">파랑</label>
        </p>
        </body>
    ```
    - 'checked' 입력시 브라우저를 열었을 때 자동으로 해당 선택지가 선택되어 있음

  * `<label>`
    - 컨트롤에 레이블(이름)을 붙이고자 할 경우 사용.

  [사용 예시]

  ```html
    <body>
      <form action="https://formspree.io/your@email.com" method="POST">

      <!-- 1 -->
        <label>이름 
        <input type="text" placeholder="이두연">
        </label>

      <!-- 2 -->
      <!-- for 값을 사용하면 input 태그를 label 태그 밖으로 꺼낼 수 있다.  -->
      <!-- 주의) for 속성의 이름과 id 속성의 이름이 반드시 동일해야 한다.  -->
      <label for="u_pass">비밀번호</label>
        <input id="u_pass" name="u_pass" type="password" maxlength="8" placeholder="비밀번호 8자리를 입력해주세요">
      </form>
    </body>
  ```

  * `<button>`
    - 버튼 폼 컨트롤로 사용자의 인터랙션을 받아 액션을 트리깅(방아쇠) 처리함.

    [type]
      - submit (초기 값) : 클릭 시 실행되는 브라우저가 열리며 폼에 입력한 정보 전송
      - button : submit과 다르게 클릭해도 아무런 변화가 없음
      - reset : 초기화 버튼

      [사용 예시]
      ```html
        <button type="submit">전송</button>
        <button type="button">버튼</button>
        <button type="reset">초기화</button>
      ```

 * `<select>`
    - 드롭 다운 메뉴(옵션을 선택 할 수 있는) 컨트롤을 말함.
      내부에 `<option>` 요소를 포함하여 사용자에게 선택할 수 있도록 한다.
      `<option>`을 묶어 그룹으로 만들고자 한다면 `<optgroup>` 요소를 사용하고,
      `label` 속성을 사용해 그룹 이름을 설정한다.

      [속성]
        - name
        - multiple : 선택지를 여러개 선택할 수 있음(값이 없음)
        - disabled
        - required
        - size

      [사용 예시]
      ```html
        <label for="user_hobby">취미</label>
        <select name="user_hobby" id="user_hobby">
          ...
        </select>
      ```

  * `<option>`
    - `<select>`, `<datalist>`, `<optgroup>` 내부에 포함 가능한 컨트롤로 항목을 만드는데 사용됨.

    [속성]
      - value
      - selected
      - label
      - disabled : 비활성화

    [사용 예시]
    ```html
      <label for="user_hobby">취미</label>
      <select name="user_hobby" id="user_hobby" required>
        <option value="0">없음</option>
        <option value="1" selected>축구</option>
        <option value="2" label="basketball" disabled>농구</option>
        <option value="3">독서</option>
        <option value="3">영화관람</option>
      </select>
    ```

  * `<optgroup>`
    - `<option>` 컨트롤을 그룹지을 때 사용됨.
    - 선택지 내에서 그룹 생성

  * [속성]
      - disabled : 해당 그룹을 비활성화
      - label : 해당 옵션만 따로 이름을 설정할 수 있음

  [사용 예시]
  ```html
    <p>
      <label for="user_hobby">취미</label>
      <select name="user_hobby" id="user_hobby" required>
        <option value="0">없음</option>
        <optgroup label="구기종목">
          <option value="1" selected>축구</option>
          <option value="2" label="basketball" disabled>농구</option>
        </optgroup>
        <optgroup label="문화생활" disabled>
          <option value="3">독서</option>
          <option value="3">영화관람</option>
        </optgroup>
      </select>
    </p>
  ```

  * `<textarea>`
    - 멀티라인 일반 텍스트 편집 컨트롤을 말한다.
    - 텍스트 박스의 크기 설정 가능. 텍스트를 길게 입력할 때 사용 

  * [속성]
    - name
    - placeholder
    - rows
    - cols
    - readonly
    - required
    - disabled
    - minlength
    - maxlength

  [사용 예시]
  ```html
    <div>
      <label for="user_comments">코멘트</label>
      <p>
        <textarea name="user_comments" id="user_comments" cols="24" rows="5">남기고 싶은 말을 작성해주세요.</textarea>
      </p>
    </div>
  ```

  * `<fieldset>`
    - 하나 이상의 폼 컨트롤을 그룹화 하는데 사용됨.

    [속성]
      - name
      - disabled

    [사용 예시]
    ```html
      <fieldset name="user_account">
        ...
      </fieldset>
    ```

  * `<legend>`
    - `<fieldset>` 컨트롤의 레이블(이름)을 설정하는 컨트롤.

    [사용 예시]
    ```html
      <fieldset name="user_account">
        <legend>사용자 계정</legend>
      </fieldset>
    ```

  * `<output>`
    - 계산된 결과를 출력하는 컨트롤.

    [속성]
      - name
      - for

    [사용 예시]
    ```html
      <form oninput="result_sum.value = parseInt(n1.value + n2.value, 10)">
        <p>
          <input type="number" name="n1" value="4"> +
          <input type="number" name="n2" value="10"> =
          <output name="result_sum">14</output>
        </p>
      </form>
    ```

  * `<datalist>`
    - 데이터 목록 요소 컨테이너 컨트롤.
      내부에 `<option>` 요소를 사용해 항목을 만든다.

      [사용 예시]
      ```html
        <label>이동할 웹주소 <input list="url_ex" type="url" name="user_url" id="user_url"></label>
        <datalist id="url_ex">
          <option value="http://naver.com">naver</option>
          <option value="http://nate.com">nate</option>
          <option value="http://google.com">google</option>
          <option value="http://goo.gl">google short url</option>
        </datalist>
      ```

  `<progress>`
    - 작업의 완료 진행 상황을 표시하는데 사용되는 컨트롤.

  * [속성]
    - value
    - max

  [사용 예시]
  ```html
    <progress value="10" max="100">10%</progress>
  ```

  * `<meter>`
    - 알려진 범위 내에서의 스칼라 측정 또는 분포 비율을 나타내는 컨트롤. (게이지(gauge)라고도 불림)
      디스크 사용 현황, 쿼리 결과의 관련성, 특정 후보에 대한 투표율 등이 해당됨.

    [속성]
      - value
      - min
      - max
      - low
      - high
      - optimum

    [사용 예시]
    ```html
      <meter value="20" min="5" max="40">20</meter>
    ```