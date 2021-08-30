# CSS (21/08/30)

## 선택자의 역할

선택자는 HTML에 스타일(CSS)을 적용하기 위해 HTML의 특정한 요소를 선택하는 사인이다.


```html
<div>
    <h1>제목..</h1>
    <p>본문..</p>
</div>
```

```css
h1 {
    color: red;
}
p {
    color: blue;
}
```
h1태그에는 빨간 글씨, 

p태그에는 파란 글씨 적용

## 속성(Properties)과 값(Value)

```css
div {
    color: red; /* 글자색은 빨강 */
    font-size: 20px; /* 글자 크기는 20px */
    width: 300px; /* 가로 너비는 300px */
    margin: 20px; /* 바깥 여백은 20px */
    padding: 10px 20px; /* 안쪽 여백은 위아래 10px, 좌우 20px */
    position: absolute; /* 위치는 부모 요소 기준 */
}
```

---
## 태그에 직접 작성하기(인라인) 선언방식

HTML 태그에 직접 작성하므로 선택자가 필요하지 않다.

```html
<div style="color: red;">태그에 직접 작성</div> <!-- red --> 
```

div 태그안에 직접 작성

단점은 4개의 div 태그에 각각 작성해야한다.

---

## HTML에 포함하기 (내장)

```html
<head>
    <style>
        div {
            color: red;
        }
    </style>
</head>
<body>
    <div>HTML에 포함1</div> <!-- red -->
    <div>HTML에 포함2</div> <!-- red -->
    <div>HTML에 포함3</div> <!-- red -->
</body>
```

div 태그에 어떤 것이 적용됐는지 확인하려면 style태그 안에 코드들을 확인한다.

---

## HTML 외부에서 불러오기 

```html
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기1</div> <!-- red -->
</body>
```
```html
<head>
  <link rel="stylesheet" href="/css/main.css">
</head>
<body>
  <div>HTML에 외부에서 불러오기2</div> <!-- red -->
</body>
```
```css
/* main.css */
div { 
  color: red;
}
/* div 선택자를 이용해서 html에 div 태그 색상을 red로 지정 */ 
```

링크 태그로 가져온 다음 일괄적으로 적용

## 선택자

HTML의 특정한 요소를 선택하는 사인

### 태그로 찾기

선택자를 입력하는 부분에 적용하려는 태그의 이름을 입력한다.

```css
/*<h1>은 글자색이 빨강이야!*/
h1 {
  color: red;
}
/*<p>는 글자색이 파랑이야!*/
p {
  color: blue;
}
```

### 클래스로 찾기

좀 더 명확하게 원하는 요소를 찾기 위해서 **클래스 선택자**라는 것이 존재한다.

```css
/*class="title"은 글자색이 빨강이야!*/
.title {
  color: red;
}
/*class="main-text"는 글자색이 파랑이야!*/
.main-text {
  color: blue;
}
```
.title의 의미는 class="title"인 요소를 찾아서 css내용을 적용
.main-text의 의미는 class="main-text"인 요소를 찾아서 css내용을 적용

```html
<h1 class="title">제목1</h1> <!--red-->
<h1>제목2</h1>
<p class="main-text">본문1</p> <!--blue-->
<p>본문2</p>
```