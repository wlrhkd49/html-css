# 선택자 (Selector) (21/09/11)

## 기본 선택자(Basic Selector)

1. 전체 선택자(Universal Selector)

(요소 내부의) 모든 요소를 선택

`*`

```css
* {
    color: red;
}
```

1. 태그 선택자(Type Selector)

태그 이름이 `E`인 요소 선택 (div, img, span, table, h1, h3)

`E`

```css
li {
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> <!--선택-->
        <li>사과</li> <!--선택-->
        <li>사과</li> <!--선택-->
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span>오렌지</span>
</div>
```


1. 클래스 선택자(Class Selector)
HTML class 속성의 값이 E인 요소 선택

`.E`

```css
.orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> 
        <li>사과</li> 
        <li class="orange">사과</li> <!--선택-->
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
    <!--선택-->
</div>
```


1. 아이디 선택자(ID Selector)

HTML id속성의 값이 E인 요소 선택

`#E`
```css
#orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> 
        <li>사과</li> 
        <li id="orange" class="orange">사과</li> <!--선택-->
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
</div>
```


## 복합 선택자

1. 일치 선택자(Basic Combinator)

E와 F를 동시에 만족하는 요소 선택

`EF`

```css
/* span이라는 태그에 class가 orange */
span.orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> 
        <li>사과</li> 
        <li id="orange" class="orange">사과</li>
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span> <!--선택-->
</div>
```


1. 자식 선택자(Child Combinator)

E의 자식 요소 F를 선택

`E > F`

```css
/* ul태그를 찾고 자식 요소의 클래스가 orange인 요소를 찾음. */
ul > .orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> 
        <li>사과</li> 
        <li id="orange" class="orange">사과</li> <!--선택-->
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span>
</div>
```


1. 후손(하위) 선택자(Descendant Combinator)

E의 후손(하위) 요소 F를 선택 ('띄어쓰기'가 선택자의 기호로 사용된다.)

`E F`

```css
/* 후손: div 안의 모든 요소, 자식도 후손에 포함 */
/* div태그를 찾아서 그것의 후손이 orange인 클래스를 찾는다. */
div .orange{
    color: red;
}
```

```html
<div>
    <ul>
        <li>사과</li> 
        <li>사과</li> 
        <li id="orange" class="orange">사과</li> <!--선택-->
    </ul>
    <div>당근</div>
    <p>토마토</p>
    <span class="orange">오렌지</span> <!--선택-->
</div>
```


1. 인접 형제 선택자(Adjacent Sibling Combinator)

E의 **다음** 형제 요소 F 하나만 선택

`E + F`

```css
/* 인접한 다음 형제 찾음 */
.orange + li {
    color: red;
}
```

```html
<ul>
    <li>딸기</li>
    <li>수박</li>
    <li class="orange">오렌지</li>
    <li>망고</li> <!--선택-->
    <li>사과</li>
</ul>
```


1.  일반 형제 선택자(General Sibling Combinator)

E의 **다음** 형제 요소 F모두 선택

`E ~ F`

```css
/* orange클래스 가진 요소 기준으로 (다음) 일반적인 형제 li태그 찾음 */
.orange ~ li {
    color: red;
}
```

```html
<ul>
    <li>딸기</li>
    <li>수박</li>
    <li class="orange">오렌지</li>
    <li>망고</li> <!--선택-->
    <li>사과</li> <!--선택-->
</ul>
```


## 가상 클래스 선택자(Pseudo-Classes Selectors)


1. HOVER

E에 마우스(포인터)가 올라가 있는 동안에만 E선택

`E:hover`


1. ACTIVE

E를 마우스로 클릭하는 동안에만 E선택

`E:active`


1. FOCUS

E가 포커스 된 동안에만 E선택 (대화형 콘텐츠에서 사용가능)<br>
대화형 콘텐츠 : input, img, tabindex

`E:focus`


1. FISRT CHILD

E가 형제 요소 중 첫번쨰 요소라면 선택

`E:first-child`

```css
/* 띄어쓰기는 후손 선택자 */
/* fruits 클래스 아래의 모든 후손 요소 중에 첫번째 자식 요소 선택 */
.fruits li:first-child {
    color: red;
}
```

```html
<ul class="fruits">
    <li>딸기</li> <!--선택-->
    <li>수박</li>
    <li>오렌지</li>
    <li>망고</li> 
    <li>사과</li> 
</ul>
```


1. LAST CHILD

E가 형제 요소 중 마지막 요소 선택

`E:last-child`

```css
/* 띄어쓰기는 후손 선택자 */
/* fruits 클래스 아래의 모든 후손 요소 중에 마지막 자식 요소 선택 */
.fruits li:last-child {
    color: red;
}
```

```html
<ul class="fruits">
    <li>딸기</li> 
    <li>수박</li>
    <li>오렌지</li>
    <li>망고</li> 
    <li>사과</li> <!--선택-->
</ul>
```


1. NTH CHILD

E가 형제 요소 중 n번째 요소라면 선택<br>
(n 키워드 사용시 0부터 해석(Zero-base))

`E:nth-child(n)`

```css
.fruits li:nth-child(2) {
    color: red;
}
```

```html
<ul class="fruits">
    <li>딸기</li> 
    <li>수박</li> <!--선택-->
    <li>오렌지</li>
    <li>망고</li> 
    <li>사과</li> 
</ul>
```

```css
/* 짝수번째 요소를 찾음 */
/* n은 0부터 대입된다! */
.fruits li:nth-child(2n) {
    color: red;
}
```

```html
<ul class="fruits">
    <li>딸기</li> 
    <li>수박</li> <!--선택-->
    <li>오렌지</li>
    <li>망고</li> <!--선택-->
    <li>사과</li> 
</ul>
```

```css
/* 3번째 요소부터 이후 요소를 찾음 */
.fruits li:nth-child(n+3) {
    color: red;
}
```

```html
<ul class="fruits">
    <li>딸기</li> 
    <li>수박</li> 
    <li>오렌지</li> <!--선택-->
    <li>망고</li> <!--선택-->
    <li>사과</li> <!--선택-->
</ul>
```

```css
/* 첫번째 요소가 p태그이고 fruits라는 요소를 가진 요소의 후손이다*/
/* 오른쪽에서 왼쪽으로 해석하는 방식이 올바름 */
.fruits p:nth-child(1) {
    color: red;
}
```

```html
<div class="fruits">
    <div>딸기</div> 
    <p>수박</p>
    <p>오렌지</p>  
    <span>사과</span>
</div>
```

-> .fruits의 첫번째 자식 요소가 `<p>`가 아니기 때문에 선택되지 않는다.


1. NTH OF TYPE

E의 타입(태그이름)과 동일한 타입인 형제 요소 중 E가 n번째 요소라면 선택<br>
(n 키워드 사용시 0부터 해석(Zero-base))

`E:nth-of-type(n)`


1. 부정 선택자(Negation Selector)

S 가 아닌 E 선택

`E:not (S)`

```html
<ul class="fruits">
    <li>오렌지</li>
    <li class="strawberry">딸기</li>
    <li>망고</li>
    <li>사과</li>
</ul>
```

```css
.fruits {
    font-size: 40px;
}
.fruits li:not(.strawberry) {
    color: red;
}
```


## 가상 요소 선택자(Pseudo-Elements Selectors) (:: 콜론이 두개 붙음)


1. BEFORE

E 요소 **내부의 앞**에, 내용을 삽입<br>
content 속성 필수!! 

`E::before`


2. AFTER

E 요소 **내부의 뒤**에, 내용을 삽입<br>
content 속성 필수!! 

`E::after`


## 속성 선택자(Attribute Selectors)

1. ATTR

속성 attr을 포함한 요소 선택

`[attr]`


2. ATTR=VALUE

속성 attr을 포함하며 속성 값이 value 인 요소 선택

`[attr=value]`


3. ATTR^=VALUE

속성 attr을 포함하며 속성 값이 value로 시작하는 요소 선택

`[attr^=value]`


4. ATTR$=VALUE

속성 attr을 포함하며 속성 값이 value로 끝나는 요소 선택

`[attr$=value]`


## 상속(Inheritance)

상속되는 속성들

- font
    - font-size
    - font-weight
    - font-style
    - line-height
    - font-family
- color
- text-align
- text-indent
- text-decoration
- letter-spacing
- opacity

강제 상속

```html
<div class="parent">
    <div class="child"></div>
</div>
```

```css
.parent {
    position: absolute; /* 상속되지 않는 속성과 값 */
}
.child {
    position: inherit; /* 강제 상속 받아 position: absolute; 와 동일 */
}
```

상속되지 않는 속성도 inherit라는 값을 사용하여 부모에서 자식으로 강제 상속 시킬 수 있지만 자식을 제외한 후손에게는 적용되지 않으며 모든 속성이 강제 상속을 사용할 수 있는 것은 아니다.


## 우선순위

```html
<body>
    <div id="color_yellow" class="color_green" style="color: orange;">Hello world</div>
</body>
```

```css
div {
    color: red !important/* !important */
}
#color_yellow {
    color: yellow; /* 아이디 선택자 */
}
.color_green {
    color: green; /* 클래스 선택자 */
}
div {
    color: blue; /* 태그 선택자 */
}
* {
    color: darkblue; /* 전체 선택자 */
}
body {
    color: violet; /* 상속 */
}
```

**우선순위 결정**

같은 요소가 여러 선언의 대상이 될 경우, 어떤 선언의 CSS 속성을 우선 적용할지 결정하는 방법<br>
1.명시도 점수가 높은 선언이 우선 (명시도)<br>
2.점수가 같은 경우, 가장 마지막에 해석되는 선언이 우선 (선언 순서)<br>
3.명시도는 '상속'규칙보다 우선 (중요도)<br>
4.`!important`가 적용된 선언 방식이 다른 모든 방식보다 우선 (중요도)<br>

1. !important 무한pt
2. 인라인 선언 방식 1000pt
3. 아이디 선택자 100pt
4. 클래스 선택자 10pt
5. 태그 선택자 1pt 
6. 전체 선택자 0pt
7. 상속 (항상 우선하지 않음)

```css
.list li.item { color: red; } /*21pt*/

.list li:hover { color: red; } /*21pt*/

.box::before { content: "Good"; color: red; } /*11pt*/

#submit span { color: red; } /*101pt*/

header .menu li:nth-child(2) { color: red; } /*22pt*/

h1 { color: red; } /*1pt*/

:not .box { color: red; } /*10pt*/
/*not은 점수 계산 x*/

:not span { color: red; } /*1pt*/
```

