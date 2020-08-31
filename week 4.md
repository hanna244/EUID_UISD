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



### [Flex 컨테이너(부모) 요소 속성]
   
   * Flex 컨테이너 플로우 축(axis)
        * 행과 열을 기준점으로 주 축(main axis)과 교차 축(cross axis)이 설정된다.    
        main axis start / cross axis start   
        main axis end   / cross axis end    

### `display`
  * flex요소를 사용하는 첫 시작은 부모요소에 `display:flex`을 적용하는 것이다.  
  자동으로 자식요소들은 모두 flex-item이 된다. (단, 자식만 item이 되는 것이다.)


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
            height: 200px; /* 컨테이너 박스의 높이가 높아지면 아이템 박스 사이의 공간도 많아진다. */
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
  - 기본값 : 1
  - 아이템 박스의 크기를 줄인다.
  - 특정한 item의 크기를 설정한 basis값 만큼 고정한다. (반드시 basis의 값이 있어야 적용가능)

```html
    <style>
        <!-- 1 -->
        .flex-item:nth-child(1) {
        flex-basis: 150px;
        flex-shrink: 0;  <!-- 값이 0일 때, 크기 고정. -->
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




  





