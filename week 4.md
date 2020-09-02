# EUID_UISD

# 1day

## 플렉시블 레이아웃 (Flexible Layout)
  * 
    ```html
        <html>
        <head>
            <style>
                .flex-container {
                display: flex;  /* 기본값 flex-direction: row */
                }
            </style>
        </head>
        <body>
            <div class="flex-container">
                <div class="flex-item">F</div>
                <div class="flex-item">L</div>
                <div class="flex-item">E</div>
                <div class="flex-item">X</div>
            </div>
        </body>
        </html>
    ```

### 참고
  * CSS 모던 레이아웃 - Flexbox 인터랙티브 플레이그라운드 : <https://codepen.io/yamoo9/full/qoGqaE>


### [Flex 컨테이너(부모) 요소 속성]
   
   * Flex 컨테이너 플로우 축(axis)
        * 행과 열을 기준점으로 주 축(main axis)과 교차 축(cross axis)이 설정된다.    
        main axis start / cross axis start   
        main axis end   / cross axis end    

### `display`
  * flex요소를 사용하는 첫 시작은 부모요소에 `display:flex`을 적용하는 것이다.  
  자동으로 자식요소들은 모두 flex-item이 된다. (단, 자식만 item이 되는 것이다.)
  * flex   
    inline-flex


### `flex-direction`
  * 주축의 방향을 정렬한다.   
    : `<row>`(기본값) `<row-reverse>` `<column>` `<column-reverse>`  
      row(행) : 행의 방향으로 정렬   
      column(행) : 열의 방향으로 정렬


### `flex-wrap`
  * 부모 컨테이너 보다 자식 아이템들의 크기가 크다면 컨테이너 박스를 넘처난 아이템은 줄바꿈하여 아래로 내려간다.
  * nowrap   
    wrap   
    wrap-reverse(교차축을 반대로)

  ```html
    <html>
    <head>
        <style>
            .flex-container {
                flex-wrap: wrap;
                width: 200px; /* 컨테이너 박스의 높이가 높아지면 아이템 박스 사이의 공간도 많아진다. */
            }
            .flex-item {
                flex-shrink: 0; /* ㄴshrink의 기본값 1은 아이템 박스가 부모 컨테이너의 크기에 맞추기 때문에 0으로 설정해 주어야 한다.*/
                width: 120px; /* 아이템들의 크기를 합한 값이 컨테이너 박스보다 크도록 */
            }
        </style>
    </head>
    </html>
  ```

### `align-items`
  * 각 아이템 개별적으로 제어하며 수직과 관련된 정열을 설정.
  * stretch을 제외한 나머지 값들은 컨텐츠 크기에 맞게 아이템의 크기가 조정된다.   

stretch(기본값) : 아이템은 컨테이너의 높이 값과 같아짐   
flex-start      : 아이템이 컨테이너 안에서 맨 위에 위치   
flex-end       : 아이템이 컨테이너 안에서 맨 아래에 위치   
center         : 아이템이 컨테이너 가운데에 위치    
baseline       : 아이템의 컨텐츠들이 컨테이너 가운데 밑줄에 맞춰서 배열됨


### `align-content`
  * 아이템들의 그룹을 제어하며 수직과 관련된 정열을 설정.
  * `flex-direction`에서 주축의 방향이 바뀜에 따라 같이 바뀐다. 

    stretch(기본값)   
    flex-start   
    flex-end   
    center   
    space-between   
    space-around   
    space-evenly   

### `justify-content`
- 수평과 관련된 정열을 설정할 때 사용.
* `flex-direction`에서 주축의 방향이 바뀜에 따라 같이 바뀐다. 
* stretch값이 없는 대신 grow를 1로 적용해 주면 stretch를 적용한 것 처럼 나타난다. 

flex-start     
center      
flex-end    
space-between : 컨테이너 박스 양 끝에 공간이 없으며 아이템들 사이에 균일하게 공간을 만듬.    
space-around : 컨테이너 박스 양 끝에 공간이 있으며 아이템들 사이에 균일하게 공간을 만듬.     
space-evenly : space-around값과 비슷하나 차이점은 컨테이너 박스 양끝의 공간의 크기를 같게    만들어줌.


```html
    <style>
        body {
            display: flex;
            justify-content: center;
        }
    </style>
```

### [flex 아이템(자식) 요소 속성]


### `flex-Grow` 
- 기본값 : 0
- 아이템 박스의 크기를 늘린다. 
- 컨테이너 박스를 각 item이 설정한 grow 값만큼 공평하게 나눠갖는다. 
- 만약 여러 item중 한 개의 크기를 더 크게 만들고 싶다면 해당 item에 grow속성을 추가로 적용한다. 

    ```html
    <style>
        <!-- 1 -->
    .flex-item {
    flex-grow: 1; <!-- 아이템을 5개로 지정했을 때 각 아이템이 5/1만큼씩 컨테이너 공간을 나눠가진다 -->
    }
    .flex-item:nth-child(2) {
    flex-grow: 2; <!-- 6/2만큼의 공간을 가져간다. -->
    }

        <!-- 2 -->
        <!-- 값이 0일 때 -->
    .flex-item {
    flex-grow: 0;
    }
    .flex-item:nth-child(2) {
    flex-grow: 2; <!-- 컨테이너박스의 남은 여백 공간을 모두 가져간다. 또한 해당 자식요소의 grow속성에 어떠한 값을 적용해도 똑같이 렌더링된다. -->
    }
    </style>
    ```

### `flex-shrink`
  - 기본값 : 1 (부모 컨테이너의 크기에 맞추게됨)
  - 아이템 박스의 크기를 줄인다.
  - 특정한 item의 크기를 설정한 basis값 만큼 고정한다. (반드시 basis의 값이 있어야 적용가능)

```html
    <style>
        <!-- 1 -->
        .flex-item:nth-child(1) {
        flex-basis: 150px;
        flex-shrink: 0;  <!-- 값이 0일 때, 설정한 크기 고정. -->
        }

        <!-- 2 -->
        .flex-item:nth-child(1) {
        flex-basis: 150px;
        flex-shrink: 1;  <!-- 3/1만큼 줄어듬 -->
        }
        .flex-item:nth-child(2) {
        flex-basis: 150px;
        flex-shrink: 2;  <!-- 3/2만큼 줄어듬 -->
        }
    </style>
```  


### `flex-Basis`
      - item의 크기를 정한다. 

        ```html
            <style>
            .flex-item:nth-child(2) {
            flex-basis: 200px;
            }
            </style>
        ```

### flex(속기형)
```css
.flex-item {
    flex: grow shrink basis; /* 기본값 : 0 1 auto*/
}
```


### order
  * 아이템 순서 설정
  * 원래는 마크업 순서대로 렌더링되지만 order속성을 사용해서 특정 아이템 박스의 위치를 임의로 설정가능하다. 
  * `order`값이 같은 경우 마크업된 순서로 우선권을 가진다.

```css
.flex-item {
  width: 50px;  
  height: 50px;
  margin-bottom: 1px;
  font-size: 2rem;
  line-height: 1;
  color: #fff;
}

.flex-item:nth-child(1) { order: -1; background: #d9727b; }
.flex-item:nth-child(2) { order: 0; background: #735454; }
.flex-item:nth-child(3) { order: -2; background: #342c40; }
.flex-item:nth-child(4) { order: 0; background: #f2ad94; }
```

### align-self
  * 자식 자신에게 속성을 적용할 때 사용
  * auto/ flex-start/ flex-end/ center/ baseline/ stretch

  ```css
  .flex-item:nth-child(1) { align-self: flex-start; background: #d9727b; }

   /* 또는 */
  .flex-item:nth-child(1) { 
      flex: 2 0 20px;
      height: 100px;
      align-self: flex-start; 
      background: #d9727b; 
  }
  ```

---
# 2day

## 질문


## 그리드 레이아웃
  * Flex와 비슷하지만 차이점이 있다. 
    - Flex는 한 뱡향으로만 설정가능한 레이아웃 시스템이고 (1차원)
    - Grid는 두 뱡향(가로/세로)으로 설정가능한 레이아웃 시스템이다. (2차원) / css 레이아웃 끝판왕(아직까지는)

### 그리드 용어 정리

  * [그리드 라인 Grid Line]
    + 그리드를 그리는 가로/세로 선을 말한다.
    + 순서를 가지고 있으며 번호로 나타난다. (row1, 2, 3/ column1, 2, 3)

  * [그리드 트랙 Grid Track]
    + 수직/수평 2개의 그리드 라인 사이 연속된 공간을 그리드 트랙이라고 한다. (로우 또는 컬럼으로 이해할 수 있다.)

  * [그리드 셀 Grid Cell]
    + 4개의 그리드 라인이 모여 그려지는 공간이 그리드 셀이다. (유닛으로 부르기도 한다.)

  * [그리드 영역 Grid Area]
    + 4개의 그리드 라인이 모여 그려지는 공간으로 셀이 묶인 영역을 그리드 에어리어라고 한다. 

  * [그리드 거터 Grid Gutters]
    + 로우, 컬럼 사이(또는 셀과 셀 사이) 간격을 그리드 거터라고 하며, 방향에 따라 로우 거터, 컬럼 거터로 나눌 수 있다. (grid-gap 속성으로 제어한다.)

  * [그리드 컨테이너]
    + 그리드의 전체 영역 
    + 그리드 아이템의 부모요소이다. 
  
  * [그리드 아이템]
    + 그리드 컨테이너의 자식 요소들이다. (직계 자식만)

  * 그리드 용어 정리 : <https://codepen.io/yamoo9/pen/odgNQj>


### 그리드 설정 - Grid 컨테이너

#### `display`
  * 그리드 컨테이너 요소를 설정하고 그리드 포멧팅 컨텍스트(격자무늬) 영역을 생성한다. 
  * flex와 마찬가지로 `display: grid;`를 적용하는 것이 그리드의 시작이다. 
  * `display: grid;`만 입력했을 때 아무런 변화도 일어나지 않는다.
    - `<grid>` : 
      `<inline-grid>` : block과 inline-block을 생각해보면 이해가 쉽다. inline-block 처럼 적용된다.  
      `<subgrid>` (Level2에서 지원 예정)
    ```css
      .grid-container {
        display: grid;  /* display: inline-grid; */
      }
    ```
  * `<float>` `<clear>` `<column>` `<vertical-align>` 속성은 그리드 컨테이너 요소에 적용되지 않는다. 
  
#### `grid-template-rows`/ `grid-template-columns` (명시적)
  * 공백으로 구분된 값 리스트를 해석하여 그리드 행, 열을 설정합니다. 각 값은 트랙의 크기를 말합니다. 
  * 컨테이너의 그리드 트랙의 크기를 지정해 준다.
  * 행과 열에 입력하는 크기에 갯수에 맞춰 행과 열이 생성된다. 
  * 단위 : px, rem, em, %, fr 등
    + auto : 자동 설정 (브라우저 크기에 따라 자동으로 변경됨.)
  * rows, columns 타이핑할 때 s 오타 조심하기!!!!!
  * 예를들어 2행 4열의 그리드를 만들었을 때 아이템의 갯수가 6개라면 나머지 두 셀은 공백으로 남겨진다. 
  ```css
  .grid { 
    display: grid;
    grid-template-rows: 20% 100px auto;      /* 3행 */
    grid-template-columns: 40px 100px;       /* 2열 */
    /* grid-template-columns: 80px auto */
    /* grid-template-columns: repeat(5, 1fr); */
    /* grid-template-columns: 150px 1.5fr 2fr */
  
  /* 속기형 */
  /* grid-template: row values / column values; */
    grid-template: ; repeat(5, 20px) / repeat(3, 1fr) 
  }

  ```

#### `grid-row-gap` `grid-column-gap` `grid-gap`

  ```css
  .grid { 
    display: grid;
    grid-row-gap: 20px;      
    grid-column-gap: 10px;   

    /* 속기형 : row column */
    grid-gap: 10px; /* 행과 열에 동일한 값 적용 */
    grid-gap: 10px 20px; 
  }
  ```

#### fr(Fraction) 단위
  - 컨테이너 전체 크기에서 숫자의 비율대로 트랙을 나눈다
```css
  .grid { 
    display: grid;
    grid-template-columns: 2fr 1.3fr 1fr; /* 트랙을 2:1.3:1의 비율로 나눈다. */
  }
```

#### repeat() 함수
  - 반복되는 값을 자동으로 처리할 수 있는 함수이다.
  - repeat(반복횟수, 반복하는 값)
    + 반복횟수 : 양수만 가능, 1이상 / 반복하는 값 : 그리드 트랙 리스트(배열)
```css
  .grid { 
    display: grid;
    grid-template-rows: repeat(5, 1fr); 
    grid-template-columns: 1fr 1fr 1fr 1fr 1fr;
    /* grid-template-rows: repeat(2, 1fr 2fr); 
    grid-template-columns: 1fr 2fr 1fr 2fr; */
  }
```

#### minmax() 함수
  * 최소값과 최대값을 지정할 수 있는 함수이다. 
  * repeat() 함수 내부, 외부에서 사용할 수 있다.
  * minmax(최소값, 최대값)
    + 부모 컨테이너의 크기가 최소값 미만으로 작아지지 않도록, 최대값 초과로 늘어나지 않도록 설정한다. 
```css
  .grid { 
    display: grid;

    /* 1, 2행 : 최소값 20px을 가지며 셀 안의 내용이 많아질 수록 트랙의 높이값이 자동으로 늘어난다 */
    grid-template-rows: repeat(2, minmax(20px, auto));
    /* grid-template-rows: repeat(2, minmax(20px, 1fr)); */


    /* 1열 : 최소값 30px을 가지며 셀 안의 내용이 많아질 수록 트랙의 너비의 값이 자동으로 늘어난다.
       2, 3열 : 1열의 너비를 제외한 나머지 공백의 공간을 1:1의 비율만큼 나눠가진다. */
    grid-template-columns: minmax(30px, auto) repeat(2, 1fr);
  }
```

#### `grid-auto-rows` `grid-auto-columns` (암시적 Implict)
  * 암시적인 그리드 트랙이란?
    + 사용자가 설정하지 않은 임의의 트랙으로, 사용자가 명시적으로 `grid-template-rows` /  `grid-template-columns` 속성을 설정하지 않은 나머지 그리드 트랙을 가리킨다. 
    + 즉, 아이템 박스는 생성되어 있으나 `grid-template-rows` /  `grid-template-columns` 속성이 설정되어 있지 않은 트랙을 말한다. 
  * 단위 : px, rem, em, %, fr 등
  * **속기형 없음**
  * grid-auto-columns : <https://developer.mozilla.org/ko/docs/Web/CSS/grid-auto-columns>    
    grid-auto-rows    : <https://developer.mozilla.org/ko/docs/Web/CSS/grid-auto-rows>    

```css
  .grid { 
    display: grid;

    grid-auto-rows: minmax(100px, auto);

    /* min-content : 컨텐트의 개수 만큼 공간박스 설정 */ 
    grid-auto-columns: min-content;
  }
```

#### `grid-auto-flow`
  * 아이템이 자동 배치되는 흐름을 결정하는 속성입니다.
    + row (기본값) : 각 행을 차례로 채우고 필요에 따라 새 행을 추가하는 자동 배치 알고리즘    
    + column : 각 열을 차례로 채우고 필요에 따라 새 열을 추가하는 자동 배치 알고리즘     
    + dense 
      - 배치 중 나중에 크기가 작은 아이템이 존재할 경우, 그리드 영역 앞부분의 남은 공간에 자동 배치하는 알고리즘 
      - row와 column에 따라 기준이 달라진다. 
    + row dense     
    + column dense 

```html
  <section class="grid-contianer">
    <div class="item-a">item-a</div>
    <div class="item-b">item-a</div>
    <div class="item-c">item-a</div>
    <div class="item-d">item-a</div>
    <div class="item-e">item-a</div>
  </section> 
```
```css
  .grid-contianer {
    display: grid;
    grid-template: repeat(5, 60px) / repeat(2, 30px);
    grid-auto-flow: row;
  }
  
  .item-a {
    grid-row: 1 / 3;
    grid-column: 1;
  }

  .item-e {
    grid-row: 1 / 3;
    grid-column: 5;
  }
```

#### `justify-items` `align-items` 아이템 내부 콘텐츠 가로/세로 정렬
  * `justify-items` : 행(row) 축을 따라 그리드 아이템 내부 콘텐츠를 정열한다. 
  * `align-items` : 열(column) 축을 따라 그리드 아이템 내부 콘텐츠를 정렬한다. 
  * 이 설정은 그리드 컨테이너 내부 모든 그리드 아이템에 적용된다. 
  
  * 값
    + stretch(기본값) : 그리드 영역 전체 너비를 채움 
    + start : 그리드 영역의 시작점에 콘텐츠 정렬
    + center : 그리드 영역의 끝점에 콘텐츠 정렬
    + end : 그리드 영역 중앙에 콘텐츠 정렬

 
#### `justify-content` `align-content` : 아이템 트랙 가로/세로 정렬
  * `justify-content` : 행(row) 축을 따라 아이템 트랙을 정렬한다. 
  * `align-content` : 열(column) 축을 따라 아이템 트랙을 정렬한다. 
  * 그리드 아이템들의 너비의 총 합이 그리드 컨테이너의 크기보다 작아야 한다.
  * 그리드 아이템들에 설정되어 있는 너비값의 단위가 같아야 한다. (px 등)

  * 값
   + stretch : 그리드 컨테이너 영역을 아이템 트랙 크기를 조정하여 채움
   + start : 그리드 컨테이너 영역의 시작점에 아이템 트랙을 정렬
   + center : 중앙에 아이템 트랙을 정렬
   + end : 끝점에 아이템 트랙을 정렬
   + space-around : 그리드 컨테이너의 남은 영역을 아이템 트랙(행)이 좌/우 공간으로 나눔 (양 가장자리 공간은 아이템 그룹 사이 간격의 1/2)
   + space-between : 그리드 컨테이너 영역의 양 가장자리 공백 없이, 아이템 트랙(행) 사이 공간을 나눔
   + space-evenly : `space-around`와 비슷해보이지만, 공간을 모두 동일하게 나누는 점이 다름

```css
  .grid {
    display: grid;

    justify-items: center;
    align-items: center;
    justify-content: center;
    align-content: center;
  }
```
   

### 그리드 설정 - Grid 아이템

#### `grid-column-start` `grid-column-end` `grid-column` `grid-row-start` `grid-row-end` `grid-row`
  * 각 셀의 영역을 지정한다. 
  * 음수값을 사용해서 끝 점에서의 상대적 위치 이동도 가능하다. 

```css
  .grid { 
    display: grid;
    grid-auto-columns: repeat(3, 150px);    
    grid-auto-rows: repeat(2, 150px);
  }

  .item:nth-child(1) {
    /* 그리드 아이엠을 열[3,4] 행[2,3] 위치에 배치 */
    grid-column-start: 3;
    grid-column-end: 4;
    grid-row-start: 2;
    grid-row-end: 3; /* 그리드 라인이 1-3번까지만 있기 때문에  grid-row-end: 3;을 입력하지 않아도 정상작동 */
  }

  /* 속기형  */
  /* grid-column: start/end  */
  /* grid-row: start/end */
  .item:nth-child(1) {
    grid-column: 3/4;
    grid-row: 2/3;
 
    /* start와 end값이 같을 때 기본값: span1 */
    grid-row: 2;
  }
```


#### Grid Area의 속기형
  * grid-area : **grid-row-start / grid-column-start / grid-row-end / grid-column-end**
  * 그리드의 라인의 갯수가 많아지면 마지막 라인의 넘버를 기억하기 쉽지 않다. 그래서 마지막 라인 `-1` 을 입력해 주는 것이 편리하다. 

```css
  .item:nth-child(1) {
    grid-column: 1/3;
    grid-row: 1/2;

    /* 또는 */
    grid-area: 1 / 1 / 2 / 3
  }
```


#### Grid Span
  * 기본값 : 1  
  * 기준 라인이 중요하다.
  * 그리드 영역 선택 가능
  * span값이 start자리에 있다면 start쪽 방향으로, end자리에 있다면 end쪽 방향으로
```css
  .item:nth-child(1) {

    /* column라인 3번에서  오른쪽(end)방향으로 2칸 : grid-column: 3/5 */ 
    grid-column: 3/span 2;

    /* row라인 4번에서 위쪽(start)방향으로 3칸 : grid-row: 1/4 */
    grid-row: span 3/4;
  }
```

#### `order`
  * 그리드 아이템을 재 정렬한다. 
  * 단, 순서를 변경해도 접근성에 문제가 발생하지 않는 경우에만 사용해야 한다. 
  * 기본값 : 0

```css
  .grid { 
    display: grid;
    grid-template-rows: repeat(3, 1fr); 
    grid-template-columns: repeat(3, minmax(50px, auto));
  }

  /* 모든 아이템의 기본값은 0이기 때문에 1번 아이템에 오더값을 4를 준다고 해서 4번 째 칸으로 이동하지 않고 맨 마지막 칸으로 이동한다. */
  .item:nth-child(1) { order: 4; }
  .item:nth-child(2) { order: 0; }
  .item:nth-child(3) { order: 0; }
  .item:nth-child(4) { order: 0; }
  .item:nth-child(5) { order: 0; }
  .item:nth-child(6) { order: 0; }

  /* 부모 컨테이너에 렌더링되는 아이템 번호 순서는 4,2,6,1,3,5 이다. */
  .item:nth-child(1) { order: 4; }
  .item:nth-child(2) { order: 2; }
  .item:nth-child(3) { order: 5; }
  .item:nth-child(4) { order: 1; }
  .item:nth-child(5) { order: 6; }
  .item:nth-child(6) { order: 3; }
```

#### `grid-template-areas`
  * 각 그리드 영역에 이름을 붙이고, 그 이름을 사용해서 배치한다. 
  * 셀의 개수 만큼 해당 위치에 이름을 입력한다.
  * 그리드 영역 이름을 반복하면 그리드 셀을 병합(merge, span)한다. 
  * 마침표 (.)는 비어있는 그리드 셀을 의미한다. (빈칸으로 표시됨)


  ```css
  /* 각 열과 행을 식별자 이름으로 구분시켜준다. */
  .grid {
    grid-template-areas:
      "header header header"      /* 1행: 3열 모두 header */
      "sidebar content1 content2" /* 1행: 1열 sidebar, 1열 content1, 1열 content2 */
      "sidebar content3 content3"
      "footer footer footer"       

      /* "   .     .      .     " */
      /* "   main  .   sidebar  " */
  }
  
  /* 그리드 영역에 식별자 이름을 입력 */
  /* 요소의 이름과 grid-area의 이름이 꼭 같은 필요는 없다. .header { grid-area: top; }  */
  .header    { grid-area: header;   }
  .sidebar   { grid-area: sidebar;  }
  .content-1 { grid-area: content1; }
  .content-2 { grid-area: content2; }
  .content-3 { grid-area: content3; }
  .footer    { grid-area: footer;   }
  ```

#### `justify-self` `align-self` : 개별 아이템 가로/세로 정렬
  * `justify-self` : 행(row) 축을 따라 특정한 아이템을 정렬한다. 
  * `align-self` : 열(column) 축을 따라 특정한 아이템을 정렬한다.
  
  * 값
   + stretch 
   + start 
   + center 
   + end 

    
```css
  .item.item-1 {
    justify-self: center;
    align-self: center;
  }
```

---

# 3day

  * 반응형 디자인이란?
    + 화면의 크기에 따라서 웹페이지의 각 요소들이 반응해서 동작하게 되는 것

### 유연한 그리드 레이아웃
  * 반응형 웹(RWD)에서는 픽셀이 아닌, 상대 단위(em,rem,%)를 사용해야 하기에 픽셀을 상대 단위로 바꾸는 계산식을 사용해야 한다. 
  * 사용하려는 콘텐츠뿐만 아니라 해당 브라우저의 단위도 바꿔줘야 한다. 
  

#### 반응형 엘리먼트 계산식
  * Target : context = results  (context = 부모컨테이너 폭 값)
  * Target ÷ context × 100 = (%)

```css
    /* 24px / 16px = 1.5em */
  h1 {
    font-family: Georgia, serif;
    font-size: 1.5em;
  }

    /* 700px ÷ 988px × 100 = 70.80202429% */
  h1 {
    width: 70.85%
  }
```
             

#### 테크니컬 이슈 
  * 유연한 레이아웃을 float로 구현할 경우 발생하는 테크니컬 이슈는 웹 브라우저가 퍼센트값을 픽셀값으로 변경하는 과정에서 발생한다. 
  하지만 플렉스 박스를 사용할 경우 해당 이슈는 발생하지 않는다. 

예시
```css
 /* 브라우저 디자인 */
.browser {
  display: flex;
  flex-flow: column;
  /* contenxt = 960px + padding: 1.4rem (패딩값도 잊지말기) */ 
  /* flex: 0 0 calc(960px + (1.4rem * 2)); */
  flex: 0 0 90vw;
  max-width: calc(960px + (1.4rem * 2));
  height: 640px;
  border-radius: 0.6rem;
}

/* 콘텐츠 */
.layout__fluid-grids .content-alpha {
  flex: 0 0 38.020833333%;
  /* width: 365px */
  /* 365px ÷ 960px × 100 = 38.020833333% */
}

.layout__fluid-grids .content-beta {
  flex: 0 0 61.979166667%;
  /* width: 595px */
  /* 595 ÷ 960 × 100 = 61.979166667% */
}
```

### 유연한 이미지
  * 컨테이너 요소의 폭에 맞춰 크기가 변경되는 이미지를 말함
  즉, 뷰포트 사이즈에 맞춰 크기 변경
  * 

#### 콘텐츠 이미지

예시
```css
  .responsive-scale {
    
    /* 이미지 자신을 포함하는 피규어의 폭만큼 확장됨 */
    width: 100%;

    /* 컨테이너의 폭에 맞춰서 크기가 자동으로 늘어난다. */
    height: auto;
  }
```

#### 배경 이미지
  * 간단하게 설정할 수 있는 콘텐츠 이미지와는 다르게 배경이미지 설정은 조금 복잡하다. 

예시
```css
  .responsive-scale-bg {
    
    /* 기본적으로 너비 100%, 높이 0으로 설정 */
    width: 100%;

    /* `!important`는 강제적으로 해당 스타일을 적용하는 문법 */
    height: 0 !important; 
    
    /*  배경이미지 높이는 `padding-bottom` `padding-top` 사용 */
    /* 이미지 높이 ÷ 이미지 가로 × 100 */
    padding-bottom: 66.6%; /* 960÷1440×100 */
    background-image: url(img/fluid/image-1440x960.jpg) no-repeat center;
    
    /* contain / cover */
    background-size: contain;
  }
```

### 재단 이미지
  * 이미지를 포함하는 컨테이너 요소의 폭에 맞춰 크기가 동적으로 잘려지는 이미지를 말한다. 

#### 배경이미지
```css
  .responsive-crop {
    width: 100%;
    height: 960px; 
    padding-bottom: 66.6%; /* 960÷1440×100 */
    background-image: url(img/fluid/image-1440x960.jpg) center top;
    background-size: cover;
  }
```

#### 재단 이미지 
```css
  .responsive-crop-container {
    position: relative;
    height: 120px; 
  }
  .responsive-crop-content {
    position: absolute;
    left: 50%;
    width: 100%;
    height: auto;
    transform: translateX(-50%);
  }
```

### 유연한 미디어
  * 아이프레임을 포함하는 컨테이너 요소의 폭에 맞춰 크기가 변경되는 것을 말한다. 
  * 가장 중요한 포인트는 비율!
  * 유튜브 등의 아이프레임이나 다음, 네이버 맵과 같은 지도서비스 같은 경우에 아래의 기법을 사용해야 한다. 
```css
  .responsive-container {
    position: relative;
    /* 4:3 = 75%,
       16:9 = 56.25%,
       21:9 = 42.857142857 */

    /* `padding-bottom` / `padding-top` */
    padding-bottom: 56.25%;
    height: 0;
    overflow: hidden;
    max-width: 100%;
  }
  .responsive-container iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%
  }
```


  





