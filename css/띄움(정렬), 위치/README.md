# 속성 - 띄움(정렬), 위치 (21/09/19)

## float  
요소를 좌우 방향으로 띄움(수평 정렬)  

값 | 의미 | 기본값
--- | --- | ---
none | 요소 띄움 없음 | none
left | 왼쪽으로 띄움 |
right | 오른쪽으로 띄움 |

```css
float: 방향;
```

```css
img {
    float: left;
}
```

**float 해제**

float 속성이 적용된 요소의 주위로 다른 요소들이 흐르게 되는데 이를 방지하기 위해 속성을 '해제'해야 함

1. 다음 형제요소에 clear: (left, right, both) 추가하여 해제
2. 부모요소에 overflow: (hidden, auto) 추가하여 해제
3. 부모요소에 clearfix클래스 추가하여 해제 (추천)

```html
<div class="parent clearfix">
    <div class="child"></div>
    <div class="child"></div>
</div>
```

```css
.clearfix::after { /*영역 제일 끝에 해제 */
    content: "";
    clear: both;
    display: block;
}
.child {
    float: left;
}
```

float이 있는 요소에는 float이 없는 다른 형제가 있으면 안된다!


## display 수정

float 속성이 추가된 요소는 display 속성의 값이 대부분 block으로 수정됨.  
flex, inline-flex는 float 속성 효과 없음.

```html
<span>1</span>
<span>2</span>
<span>3</span>
```

```css
span {
    width: 100px;
    height: 100px;
    margin: 10px;
    background: tomato;
    float: right; /* 속성의 값이 block으로 수정됨 */
}
```
<br>


## clear

float 속성이 적용되지 않도록 지정 (해제)

값 | 의미 | 기본값
--- | --- | ---
none | 요소 띄움(허용) | none
left | 왼쪽 띄움 해제 |
right | 오른쪽 띄움 해제 |
both | 양쪽(왼쪽, 오른쪽) 모두 띄움 해제 | 