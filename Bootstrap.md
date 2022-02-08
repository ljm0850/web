Bootstrap

- Front-end open source
- https://getbootstrap.com/docs/5.1/getting-started/introduction/

- ```html
  <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-1BmE4kWBq78iYhFldvKuhfTAU6auU8tT94WrHftjDbrCEXSU1oBoqyl2QvZ6jIW3" crossorigin="anonymous">
  ```

- ```html
  <!--bundle-->
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.1.3/dist/js/bootstrap.bundle.min.js" integrity="sha384-ka7Sk0Gln4gmtz2MlQnikT1wXgYsOg+OMhuP+IlRH9sENBO0LRn5q+8nbTov4+1p" crossorigin="anonymous"></script>
  ```

  - 위와 같이 script 입력 안하면 기능들이 표현만 될뿐 작동x

- **자세한건 docs에서 찾아보자**

## spacing(간격) 조절

- property
  - **m** - margin
  - **p** - padding
- sides
  - **t** - top
  - **b**-bottom
  - **s**-left
  - **e**-right
  - **x**-left,right
  - **y**-top,bottom
- size
  - **0** - 0rem
  - **1**-0.25rem
  - **2**-0.5rem
  - **3**-1rem
  - **4**-1.5rem
  - **5**-3rem

```css
/*mt-0는 다음과 같이 입력됨 */
.mt-0 {
    magin-top : 0 !important
}
```

```html
<div class="mx-auto" style="width: 200px;">mx-auto예제</div>
```



-----



#### text

```html
<!--(text-(start,end,center))-->
<p class="text-center">문자 중앙으로</p>

<!--(fw-(bold,normal,light)) or (fst-italic)-->
<p calss="fw-normal">noraml font로 입력</p>
```



#### display

- d-inline
- d-block
- box
- etc...



## Breakpoints

뷰포트 크기에 따라 작동방식을 바꿀때 사용

- X-Small : <576px
- Small(sm) : >=576px
- Medium(md) : >=768px
- Large(lg) : >=992px
- Extra large(xl) : >=1200px
- Extra extra large(xxl) : >1400px

```html
<div class='d-sm-flex'>sm</div>
<div class='d-md-flex'>md</div>
```





## Grid system

- 기본 요소
  - Column : 실제 컨텐츠를 가진 영역
  - Gutter:  Column 사이 간격
  - Container : Column을 담은 공간

- 기본은 12개의 column을 담을수 있음

![image-20220208120410036](Bootstrap.assets/image-20220208120410036.png)

```html
<div class="container">
  <div class="row bg-dark text-danger text-center">
      <div class="col-3">Column1</div>
      <div class="col-6 bg-primary">Column2</div>
      <div class="col-3">Column3</div>
  </div>
</div>
```

- breakpoints와 함께 디자인 하는 경우가 많음

- offset

  - ```html
    class ="offset-4 col-4"
    ```

  - 선언된 클래스 앞부분에 offset이 형성이 됨