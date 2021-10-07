# CSS / Grid
<br>

Grid는 2차원(행과 열)의 레이아웃 시스템을 제공한다.  

> CSS Grid는 예전부터 핵(Hack)으로 불린 다양한 레이아웃 대체 방식들을 해결하기 위해 만들어진 특별한 CSS 모듈

<br>

## Grid Properties
<br>

CSS Grid는 CSS Fles와 같이 Container와 Item이라는 두가지 개념으로 두분되어 있다.  
Container는 Items를 감싸는 부모 요소이며, 그 안에서 각 Item을 배치할 수 있다.
<br>


## Grid Containers
<br>

### display

Grid Container를 정의한다.  
정의된 컨테이너의 자식 요소들은 자동으로 Grid Items로 정의된다.  
> 그리드를 사용하기 위해 컨테이너에 필수로 작성한다!

값 | 의미
--- | ---
grid | Block 특성의 Grid Container 정의
inline-grid | Inline 특성의 Grid Container 정의

```css
.container {
    display: grid;
}
```

### grid-template-rows

명시적 행의 크기를 정의한다.  
동시에 라인의 이름도 정의할 수 있다.  
`fr`(fraction, 공간 비율) 단위를 사용할 수 있다.  
`repeat()`함수를 사용할 수 있다.

```css
.container {
  display: grid;
  grid-template-rows: 1행크기 2행크기 ...;
  grid-template-rows: [선이름] 1행크기 [선이름] 2행크기 [선이름] ...;
}
```

```css
/* 각 행의 크기를 정의합니다. */
.container {
  grid-template-rows: 100px 200px;
}
/* 동시에 각 라인의 이름도 정의할 수 있습니다. */
.container {
  grid-template-rows: [first] 100px [second] 200px [third];
}
/* 라인에 중복된 이름을 지정할 수 있습니다. */
.container {
  grid-template-rows: [row1-start] 100px [row1-end row2-start] 200px [row2-end];
}
```
꼭 필요한 경우가 아니면 라인의 이름을 정의하지 않기도 한다.  

> grid-template-columns와 동일하다.


### grid-template-areas

지정된 그리드 영역 이름(`grid-area`)을 참조해 그리드 템플릿을 생성한다.  

> grid-area 는 Grid Container가 아닌 Grid Item에 적용하는 속성이다.

```css
.container {
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(3, 1fr);
  grid-template-areas:
    "header header header"
    "main main aside"
    "footer footer footer";
}
header { grid-area: header; }
main   { grid-area: main;   }
aside  { grid-area: aside;  }
footer { grid-area: footer; }
```

### row-gap(grid-row-gap)

각 행과 행 사이의 간격을 지정한다.

> 그리드 선의 크기를 지정한다고 표현할 수 있다.

```css
.container {
    row-gap: 크기;
}
```

### column-gap(grid-column-gap)

각 열과 열 사이의 간격을 지정한다.

```css
.container {
    column-gap: 크기;
}
```

### gap(grid-gap)

각 행과 행, 열과 열 사이의 간격을 지정한다.

```css
.container {
  gap: <grid-row-gap> <grid-column-gap>;
}
```

```css
.container {
  display: grid;
  grid-template-rows: repeat(2, 150px);
  grid-template-columns: repeat(3, 1fr);
  gap: 20px 10px;
}
/* 하나의 값으로 통일할 수 있습니다. */
.container {
  gap: 10px;  /* row-gap: 10px; + column-gap: 10px; */
}
/* 하나의 값만 적용하고자 한다면 다음과 같이 사용할 수 있습니다. */
.container {
  gap: 10px 0; /* row-gap */
  gap: 0 10px; /* column-gap */
}
```

### grid-auto-rows

암시적 행의 크기를 정의한다.  
Item이 `grid-template-rows`로 정의한 명시적 행 외부에 배치되는 경우 암시적 행의 크기가 적용된다.


### grid-auto-columns

암시적 열의 크기를 정의한다.  
Item이 `grid-template-columns`로 정의한 명시적 행 외부에 배치되는 경우 암시적 열의 크기가 적용된다.

```css
.container {
  width: 300px;
  height: 200px;
  display: grid;
  grid-template-rows: 100px 100px;
  grid-template-columns: 150px 150px;
  grid-auto-rows: 100px;
  grid-auto-columns: 100px;
}
.item:nth-child(3) {
  grid-row: 3 / 4;
  grid-column: 3 / 4;
}
```

> 암시적 크기가 적용된 행과 열은 양수 라인 번호만 사용할 수 있고 음수는 사용이 불가능!


### grid-auto-flow

배치하지 않은 Item을 어떤 방식의 '자동 배치 알고리즘'으로 처리할 지 정의한다.  

> 배치한 아이템은 `grid-area`를 사용한 아이템을 의미

값 | 의미 | 기본값
--- | --- | ---
row | 각 행 축을 따라 차례로 배치 | row
column | 각 열 축을 따라 차례로 배치 |
row dense | 각 행 축을 따라 차례로 배치, 반 영역 메움! |
column dense | 각 열 축을 따라 차례로 배치, 반 영역 메움! |


```css
/* For row & row dense */
.container {
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  grid-auto-flow: row || row dense || dense;
}
.item:nth-child(2) {
  grid-column: span 3;
}
```

![1](https://user-images.githubusercontent.com/63788023/136402093-92f0f7b0-814b-498b-8eb4-60b7cef491e7.png)

```css
/* For column & column dense */
.container {
  display: grid;
  grid-template-rows: repeat(3, 1fr);
  grid-template-columns: repeat(3, 1fr);
  grid-auto-flow: column || column dense;
}
.item:nth-child(1) {
  grid-column: 2 / span 2;
}
.item:nth-child(2) {
  grid-column: span 2;
}
```

![1](https://user-images.githubusercontent.com/63788023/136402341-2b5a45ae-c73e-49c8-aee4-fb08d763e6a4.png)

repeat() 함수는 2번째 인수를 반복하기 뛰문에 다음과 같이 활용할 수 있다.

```css
.container {
  grid-template-columns: repeat(4, 100px 200px 50px);
  /* grid-template-columns: 100px 200px 50px 100px 200px 50px 100px 200px 50px 100px 200px 50px; */
}
.container {
  grid-template-columns: repeat(4, 1fr 2fr 3fr);
  /* grid-template-columns: 1fr 2fr 3fr 1fr 2fr 3fr 1fr 2fr 3fr 1fr 2fr 3fr; */
}
```