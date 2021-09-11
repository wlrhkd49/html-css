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