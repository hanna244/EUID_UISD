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
    + `transition-timing-function`  트랜지션 타이밍 함수
      - 트렌지션 효과가 진행하는 동안 속도의 변화를 지정    
      - linear, ease, ease-in, ease-uot, ease-in-out, cubic-bezier()
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
      - 트렌지션 효과가 시작되기 전 기다리는 시간
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



