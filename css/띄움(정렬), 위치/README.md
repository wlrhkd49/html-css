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
<br>


## position

요소의 위치 지정 방법의 유형(기준)을 설정

값 | 의미 | 기본값
--- | --- | ---
static | 유형(기준) 없음 / 배치 불가능 |static
relative | 요소 자신을 기준으로 배치 |
absolute | 위치 상 부모 요소를 기준으로 배치 |
fixed | 브라우저(뷰포트)를 기준으로 배치 |
sticky| 스크롤 영역 기준으로 배치 |

1. top

요소의 position 기준에 맞는 '위쪽'에서의 거리(위치)를 설정

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 계산 | auto
단위 | px, em, cm 등 단위로 지정 | 0
% | 부모(위치 상의 부모)요소의 세로 너비의 비율로 지정, 음수 값 허용 |

2. bottom

요소의 position 기준에 맞는 '아래쪽'에서의 거리(위치)를 설정

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 계산 | auto
단위 | px, em, cm 등 단위로 지정 | 0
% | 부모(위치 상의 부모)요소의 세로 너비의 비율로 지정, 음수 값 허용 |

3. left

요소의 position 기준에 맞는 '왼쪽'에서의 거리(위치)를 설정

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 계산 | auto
단위 | px, em, cm 등 단위로 지정 | 0
% | 부모(위치 상의 부모)요소의 가로 너비의 비율로 지정, 음수 값 허용 |

4. right

요소의 position 기준에 맞는 '오른쪽'에서의 거리(위치)를 설정

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 계산 | auto
단위 | px, em, cm 등 단위로 지정 | 0
% | 부모(위치 상의 부모)요소의 가로 너비의 비율로 지정, 음수 값 허용 |
<br>


## sticy

스크롤 영역 기준으로 배치 (IE 지원 불가)

```css
.box {
    position:sticky;
    top: 0;
}
```
<br>


## 요소 쌓임 순서(Stack order)

요소가 쌓여 있는 순서를 통해,   
어떤 요소가 사용자와 가깝게 있는지 (더 위에 샇이는지)를 결정(Z축)

1.static을 제외한 position 속성의 값이 있을 경우 가장 위에 쌓음(값은 무관)  
2.position이 모두 존재한다면 z-index 속성의 숫자 값이 높을 수록 위로 쌓임   
3.position 속성의 값이 있고, z-index 속성의 숫자값이 같다면,   
'HTML'의 마지막 코드일수록 위로 쌓임
<br>


## display 수정

absolute, fixed 속성 값이 적용된 요소는 display 속성의 값이 대부분 block으로 수정됨.

```html
<span>INLINE</span>
```

```css
span {
    width: 100px;
    height: 100px;
    background: tomato;
    margin: 30px 0;
    position: fixed or absolute; 
    /* display가 block으로 변경 */
}
```