# Web

## CSS

- 스타일을 지정하기 위한 언어

- 속성(Property) : 어떤 스타일 기능을 변경할지
- 값(Value) : 어떻게 스타일 기능을 변경할지



### CSS 정의 방법

- 인라인(inline)

  ```html
  <!DOCTYPE html>
  <html lang='ko'>
  	<body>
          <h1 style="color red";>Hello word!
          </h1>
      </body>
  </html>
  ```

- 내부참조(embedding)-`<style>`

  ```html
  <!DOCTYPE html>
  <html lang='ko'>
  	<body>
          <h1>Hello word!</h1>
    		<style>
              h1 { color:red;}
          </style>  
      </body>
  </html>
  ```

- 외부 참조

  ```html
  <!DOCTYPE html>
  <html lang="ko">
  <head>
    <!--<meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0"> -->
    <link rel="stylesheet" 
          href="외부.css">
    <title>외부 참조</title>
  </head>
  ```



### 선택자

- `*`전체 선택자

  ```css
  * {color: red;}
  ```

- `h1,p,..`요소 선택자

  ```css
  h2 {color: blue;}
  ```

- `.class`클래스 선택자 (**class = ljm** 선언하면 적용)

  ```css
  .ljm {color: green;}
  ```

- `#id` id선택자 (해당 **id**를 가진 항목 적용)

  ```css
  #nick {color: purple}
  ```

- 자식 결합자(ljm 밑의 __한단계 p__에만 적용)

  ```css
  .ljm > p {color: white;}
  ```

- 자손 결합자(ljm 밑의 __모든 p__에 적용)

  ```css
  .ljm p {color: black;}
  ```

- 일반 형제 결합자(p뒤에 오는 모든 span에 적용)

  ```css
  p ~ span {color: yellow ;}
  ```

- 인접 형제 결합자(p 바로뒤에 오는 span에 적용)

  ```css
  p + span {color: gray; }
  ```

  

### CSS 적용 순위

```
!important > inline > id > class, 속성,pseudo-class > 요소,pseudo-element
```

- pseudo-class: `:link`,`:visited`,`:hover`와 같이 상태를 명시할때 사용되는 class



### CSS 상속

- __Text__ 관련 요소(font, colot, text-align ...), __opacity__(불투명도), __visibility__ (hidden..)

- __box model,position__ 관련 요소는 __상속x__



### 크기 단위

- px
  - 모니터 해상도의 한 화소인 pixel 단위
  - 픽셀의 크기는 변하지 않기에 고정적인 단위
- %
  - 백분율 단위
  - 가변적인 레이아웃에서 자주 사용

- em
  - 상속의 영향을 받음
  - 배수 단위, 요소에 지정된 사이즈에 상대적인 사이즈를 가짐
- rem
  - 최상위 요소(html)의 사이즈 기준으로 배수 단위를 가짐
- viewport
  - 디바이스의 viewport를 기준으로 상대적인 사이즈가 결정됨
  - vw,vh,vmin,vmax



### 색상 단위

- 색상 키워드
  - 대소문자 구분없이 red,green,blue와 같이 글자로 입력
- RGB 색상
  - #+16진수 표기
  - rgb(100,80,60)
- HSL 색상
  - 색상, 채도, 명도를 통해 색을 표현
  - hsl(색상,채도%,명도)



### Box model

- __margin__
  - 테두리 바깥의 외부 여백
  - 배경색 지정x
- __border__
  - 테두리 영역
  - 실선,점선(dashed)등 적용
- __padding__
  - 테두리와 content사이 여백
  - 배경색 적용
- __content__
  - 글,이미지 등 실제 내용



### Box-sizing

- 기본적으로 box-sizing은 content-box
  - Padding을 제외한 순수 contents 영역만을 box 지정
- border까지의 영역으로 box-sizing하려면 box-sizing을 border-box로 설정

```css
box-sizing: content-box;
width: 100%;
border : solid #5B6DCD 10px;
padding: 5px;
```

```css
box-sizing: border-box;
width : 100%;
border : solid #5B6DCD 10px;
padding: 5px;
```



### Display

- **block**

  - 줄 바꿈이 일어나는 요소
  - 화면 크기 전체의 가로 폭을 차지
  - 블록 레벨 요소 안에 인라인 레벨 요소 들어갈 수 있음
  - div / ul, il, li / p / hr / form 등

- **inline**

  - 줄 바꿈이 일어나지 않는 행의 일부 요소
  - content 너비 만큼 가로 폭을 차지
  - 따라서 width, height,margin을 지정 불가
  - 상하 여백은 line-height로 지정

  - span / a / img / input, label / b, em, i,  strong 등

- __inline-block__
  - block과 inline 레벨 요소 특징을 모두 가짐
  - 한 줄에 표시 가능하고 width, height, margin 설정 가능

- __none__
  - 해당 요소를 화면에 표시하지; 않고, 공간도 부여하지 않음
  - visibility:hidden은 공간은 있으나, 화면에 표시하지 않음



### position

- __static__: 모든 태그의 기본값(기준 위치)
  - 배치 순서에 따름
  - 부모 요소 내에서 배치시 부모 요소 기준으로 배치

- __relative__ : 상대위치
  - 자기 자신의 static 위치를 기준으로 이동
  - 레이아웃에서 차지하는 공간은 변하지 않음

- __absolute__ : 절대위치
  - 부모/조상 요소를 기준으로 이동
  - 레이아웃에서 차지하는 공간이 변함

- __fixed__ : 고정위치
  - 부모 요소 관계 없이 viewport 기준으로 이동(스크롤 시에도 같은곳에 위치)



- 좌표 프로퍼티
  - top
  - bottom
  - left
  - right



#### nth-child() & nth-of-type()

- __nth-child()__는 모든 요소를 포함해서 순서를 카운팅
- __nth-of-type()__는 해당하는 타입에서부터 카운팅
- ()안에 odd , even을 넣어 홀짝 가능

```css
/* 목록의 두 번째 <li> 선택 */
li:nth-child(2) {
  color: lime;
}
```



-----



## Float

- 박스를 왼쪽(오른쪽)으로 이동시켜 텍스트를 포함한 인라인 요소들이 박스를 둘러싸게 함
- 요소가 Normal flow를 벗어나도록 함
- flexbox, Grid ...등이 나오기 전에 주로 사용

#### Float 속성

- none : 기본값
- left : 요소를 왼쪽으로
- right : 요소를 오른쪽으로

```html
<body>
    <div class="box left">
        float left
    </div>
</body>
```

```css
.box{with:100px;
    heigh:100px;
    border:3px solid black;
    color: blue;
    /* ect.. */
}
.left {
    float: left;
}
```

### Clearing Float

- Float한 이후에 그 뒤 요소들이 Float가 적용되지 않기 위해 사용 

- `::after` 선택한 요소 맨 마지막에 자식 요소를 생성하여 정리하기 위해 사용(부모 요소에 사용하여 처리)

  ```css
  .clearfix::after {
      content : "";
      display : block;
      clear : both;
  }
  ```

  

## Flexbox

- 행과 열 형태로 아이템들을 배치하는 1차원 레이아웃 모델

```css
.flex-container {
    display : flex;
    /* display: inline-flex; */
}
```

- Flex Container 와 Flex Item으로 구성

### Flex 속성

#### 배치설정

- flex-direction : Main axis 방향 설정

  - flex-direction : row;
    - x축 방향으로 Item 배열

  - flex-direction: column;
    - y축 방향으로 Item 배열

- flex-wrap
  - 아이템이 컨테이너를 벗어나는 경우 해당 영역 내에 배치되도록 설정
  - x축에서 넘어가면 y축을 한칸 늘려서 작동

#### 공간 나누기

- justify-content (main axis) & align-content (cross axis)
  - start
  - end
  - center
  - space-between : items 사이 간격을 균일하게
  - space-around : items을 둘러싼 영역을 균일하게
  - space-evenly : 전체 영역에서 아이템 간격을 균일하게

#### 정렬

- align-items (모든 아이템을 cross axis 기준으로) & align-self (개별 아이템)
  - stretch
  - flex-start
  - flex-end
  - center
  - baseline : 텍스트 baseline에 기준선을 맞춤

#### 배치 순서 변경시

- order-숫자