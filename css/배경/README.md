# CSS / 속성 - 배경 (21/09/23)

## background

요소의 배경을 설정 `단축`

값 | 의미 | 기본값
--- | --- | ---
background-color | 배경 색상 | transparent
background-image | 하나 이상의 배경 이미지 | none
background-repeat | 배경 이미지의 반복 | repeat
background-position | 배경 이미지의 위치 | 0 0
background-attachment | 배경 이미지의 스크롤 여부(특성) | scroll

```css
background: 색상 이미지경로 반복 위치 스크롤특성;
```

```css
.box1 {
    background: red url("./img/image.jpg") no-repeat left top scroll;
    /* 왼쪽 상단, 스크롤 */
}
.box2 {
    background: url("./img/image.jpg") no-repeat right 100px;
    /* 이미지경로 반복 위치 */
}
.box3 {
    background: red;
    /* 색상 */
}
```
---

### background-color

요소의 배경 색상을 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
색상 | 요소의 배경 색상 |
transparent | 투명 | transparent


### background-image

요소의 배경에 하나 이상의 이미지를 삽입 `개별` 

값 | 의미 | 기본값
--- | --- | ---
none | 이미지 없음 | none
url("경로") | 이미지경로(URL) |

```css
background-image : url("경로");
```

```css
.box {
    background-image: url("../img/image.jpg");
    width:120px;
    height:20px;
}
.box1 {
    /* 개별 속성 */
    background-image: url("../img/i1.jpg"),
    url("../img/i2.jpg"),
    url("../img/i3.jpg");
}
.box2 {
    /* 단축 속성 */
    background-image: url("../img/i1.jpg") no-repeat,
    url("../img/i2.jpg") no-repeat 100px 50px,
    url("../img/i3.jpg") repeat-x;
}
```

> 하나 이상의 배경 이미지를 삽입할 경우 ,로 구분합니다. 먼저 작성된 이미지가 더 위에 쌓입니다. 이런 "다중 배경 이미지"는 IE8 이하 버전에 사용할 수 없습니다.


### background-repeat

배경 이미지의 반복을 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
repeat | 배경 이미지를 수직, 수평으로 반복 | repeat
repeat-x | 배경 이미지를 수평으로 반복 |
repeat-y | 배경 이미지를 수직으로 반복 |
no-repeat | 반복 없음 |


### background-position

배경 이미지의 위치를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
방향 | top, bottom, left, right, center | 
% | 왼쪽 상단 모서리는 0% 0%<br>
오른쪽 하단 모서리는 100% 100% | 0% 0%
단위 | px, cm, em 등 단위로 지정 | 

**사용법**

값이 방향일 경우
`background-position: 방향1 방향2;`
<br>

값이 단위(%, px 등)일 경우
`background-position: X축 Y축`
<br>


### background-attachment

요소가 스크롤될 때 배경 이미지의 스크롤 여부 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
scroll | 배경 이미지가 요소를 따라서 같이 스크롤 됨 | scroll
fixed | 배경 이미지가 뷰포트에 고정되어, 요소와 같이 스크롤되지 않음 |
local | 요소 내 스크롤 시 배경 이미지가 같이 스크롤 됨 |


### background-size

배경 이미지의 크기를 지정

값 | 의미 | 기본값
--- | --- | ---
auto | 배경 이미지가 원래의 크기로 표시됨 | auto
단위 | px, em, % 등 단위로 지정<br> width height 형태로 입력 가능<br> width만 입력하면 비율에 맞게 지정됨 |
cover | 배경 이미지의 크기 비율을 유지하며, 요소의 더 넓은 너비에 맞춰짐<br> 이미지가 잘릴 수 있음 |
contain | 배경 이미지의 크기 비율을 유지하며, 요소의 더 짧은 너비에 맞춰짐<br> 이미지가 잘리지 않음 |

> contain은 빈공간이 생길 수 있다.



