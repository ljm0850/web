# Web

## HTML

### HTML 기본 구조

- html : 문서의 최상위 요소
- head : 문서 메타데이터 요소
  - 문서 제목, 인코딩, 스타일,파일 로딩...
- body : 본문 요소

#### head

- `<title>` : 브라우저 상단 타이틀

- `<meta>`: 문서 레벨 메타데이터

  - ```html
    <head>
        <meta charset="UTF-8">
        <meta content="origin" name="referrer">
    ```

- `<link>`: 외부 리소스 연결 요소(css 파일 등)

  - ```html
    <head>
        <link href="/manifest?pwa=webhp" crossorigin="use-credentials" rel="manifest">
    <!-- google.com 참조 -->
    ```

    - __crossorigin__:HTML에서 img,video,script와 같은 CORS(서로 다른 도메인 출처 접근,실행)를 지원하는데, 이때 요청에 대한 처리
      - anonymous : CORS요청에 자격 증명 플래그 설정X
      - use-credentials: CORS요청에 자격 증명 플래그 설정, 자격증명 요청
    - __rel__: 현재 문서와 외부 리소스 사이의 연관 관계

- `<script>`: 스크립트 요소(JS파일 등)

- `<style>`: CSS 을 직접 작성시



#### element

- 내용이 없는 태그
  - br, hr, img, input, link, meta

#### attribute

- __id__: 고유 식별자 지정
- __class__: 공백으로 구분된 해당 요소의 클래스의 목록
- __data-*__: 개인 사용자 정의 데이터를 저장하기 위해 사용
- __style__: inline 스타일
- __title__: 요소에 대한 추가 정보 지정
- __tabindex__: 요소의 탭 순서



#### 시맨틱 태그(<-> div,span)

**의미**를 담은 태그, 기능이 존재하는건 아님

- `header`: 문서 전체나 섹션의 머리말
- `nav`: 네비게이션
- `aside`사이드에 위치한 공간
- `section`:문서의 일반적인 구분,컨텐츠의 그룹 표현
- `article`: 문서,페이지,사이트 안에서 독립적으로 구분되는 영역
- `footer`: 문서 전체나 섹션의 마지막



#### 텍스트 요소

- `<a></a>`: href 속성을 활용하여 다른 URL로 연결하는 하이퍼링크 생성
- `<b></b>`,`<strong></strong>`: 굵은 글씨 
- `<i></i>`,`<em></em>`: 기울임 글씨 
- `<br>` :줄 바꿈

- `<img>`: src 속성을 활용하여 이미지 표현

- `<span></span>`: 의미 없는 인라인 컨테이너



#### 그룹 컨텐츠

- `<p></p>`: 한 문단
- `<hr>`: (horizontal rule) 수평선

- `<ol></ol>` // `<ul></ul>`: 순서가 있는//없는 리스트
- `<pre></pre>`:HTML에 작성한 내용을 그대로 표현

- `<blockquote></blockquote>`: 텍스트가 긴 인용문, 주로 들여쓰기를 한것으로 표현됨
- `<div></div>`: 의미 없는 블록 레벨 컨테이너



#### table

- `<th>`:(table head) table의 제목, 기본값으로 굵은 글씨에 중앙정렬
- `<td>`:(table data) 셀을 만드는 역할, 기본값으로 보통 글씨체에 왼쪽 정렬
- `<tr>`:가로줄을 만드는 역할

- `<caption>`: 표 설명 또는 제목



#### form, input

##### form

- 데이터를 서버에 제출하기 위한 영역
- 기본속성
  - **action**:form을 처리할 서버의 URL
  - __method__: form을 제출시 사용할 HTTP 메서드 (GET,POST)
  - __enctype__: method가 post인 경우 데이터의 유형
    - application~~ : 기본값
    - multipart/form-data : 파일 전송시

##### input

- name: form control에 적용되는 이름(이름/값 페어로 전송)
- value: form control에 적용되는 값(이름/값 페어로 전송)
- required, readonly, autofocus, autocomplete, disabled ...

###### input 유형

- text : 일반 텍스트
- password: 입력값이 *로 표현
- email : email형식만 제출 가능
- number : min,max,step 속성을 활용하여 숫자 범위 설정 가능
- file : accept 속성을 활용하여 파일 타입 지정 가능

- checkbox , radio : 다중,단일 선택
- color : 색 선택
- date : 날자 선택
- __hidden__ 사용자에게 보이지 않는 input

- 이 나중에 적혀있기에 green만 적용