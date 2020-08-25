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

