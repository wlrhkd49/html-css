# 콘텐츠 구분 & 문자 콘텐츠 (21/09/02)

## 콘텐츠 구분

  ### `<header>`

  - header태그 안에 header, footer 태그는 넣을 수 없다.

  - address태그 안에 header 태그는 넣을 수 없다.

  - 전역 속성만을 포함한다.

  ```css
  header { display: block; }
  ```


  ### `<footer>`

  - 일반적으로 작성자 구획, 저작권 데이터, 관련된 문서 링크에 대한 정보를 포함한다.

  - footer태그 안에는 header, footer 태그는 넣을 수 없다.

  ```css
  footer { display: block; }
  ```


  ### `<h1>~<h6>`

  - 6단계의 문서 제목을 구현한다.

  - 전역 속성만들 포함한다.

  - 제목 폰트의 크기를 줄이기 위해 낮은 단계를 **사용하지 않는다.** 
  대신 CSS의 font-size 속성을 사용한다.

  - 제목 단계를 건너뛰지 않는다.

  - 첫번째 단계의 제목은 한 페이지에 하나만 사용한다.


  ### `<main>`

  - 문서나 앱 `<body>`의 주요 콘텐츠를 나타낸다. 주요 콘텐츠 구역은 문서의 핵심주제나 애플리케이션의 핵심 기능성에 대해 부연, 직접적으로 연관된 콘텐츠들로 이루어진다.

  - Internet Explore는 지원하지 않는다.

  - 한 문서에 하나의 `<main>`요소만 포함 가능.

  ```css
  main { display: block; }
  ```

 ### `<article>`

 - 독립적으로 구분되거나 재사용 가능한 영역을 설정한다. (매거진/신문 기사, 블로그 등)

 - 일반적으로 `<h1><h6>`를 포함하여 식별

 - 작성일자와 시간을 `<time>`의 datetime속성으로 작성

 ```css
  article { display: block; }
```

 
 ### `<section>`

 - 문서의 일반적인 영역을 설정한다.

 - 일반적으로 `<h1><h6>`를 포함하여 식별

 - section 안에 article 들어갈 수 있다.

 - article 안에도 section 들어갈 수 있다.

 - div는 의미x, section은 의미o (제목 포함),article은 독립성 (제목 포함)

 ```css
  section { display: block; }
```


### `<aside>`

- 문서의 별도 콘텐츠를 설정. (보통 광고나 기타 링크 등의 사이드바를 설정)

```css
  aside { display: block; }
```


### `<nav>`

- 다른 페이지 링크를 제공하는 영역을 설정한다.
(Navigation, 보통 메뉴, Home, About, 목차, 색인)

- 메뉴를 묶을 때 많이 사용, `<ul>, <ol>` 사용

```css
  nav { display: block; }
```

- --> 영역을 설정하는 태그는 블록 요소!


### `<address>`

- `<body>` `<article>` `<footer>` 등에서 연락처 정보를 제공하기 위해 포함하여 사용한다.

```css
  address { display: block; }
```

### `<div>`

- 본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정한다.<br>
(Division, 꾸미는 목적으로 사용)

```css
  div { display: block; }
```