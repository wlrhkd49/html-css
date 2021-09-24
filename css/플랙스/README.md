# CSS / 속성 - 플랙스 (21/09/24)

## CSS3 Flexible Box

Flex는 요소의 크기가 불분명하거나 동적인 경우에도, 각 요소를 정렬할 수 있는 효율적인 방법을 제공합니다.  
<br>
우선 Flex는 2개의 개념으로 나뉩니다.  
첫 번째는 Container 두 번째는 Items 입니다.  
위에서 살펴본 바와 같이 Container는 Items를 감싸는 부모 요소이며, 각 Item을 정렬하기 위해선 Container가 필수입니다.  
<br>
주의할 부분은 Container와 Items에 적용하는 속성이 구분되어 있다는 것입니다.  
Container에는 display, flex-flow, justify-content 등의 속성을 사용할 수 있으며,  
Items에는 order, flex, align-self 등의 속성을 사용할 수 있습니다.  


## Flex Container 

Flex Container를 위한 속성들은 다음과 같다.  
주 축과 교차 축의 개념은 뒤에서 살펴보자.

속성 | 의미
--- | ---
display | Flex Container 정의
flex-flow | `flex-direction`와 `flex-wrap`의 단축 속성
flex-direction | Flex Items의 주축을 설정
flex-wrap | Flex Items의 여러 줄 묶음(줄 바꿈) 설정
justify-content | 주 축의 정렬 방법을 설정
align-content | 교차 축의 정렬 방법을 설정 (2줄 이상)
align-items | 교차 축에서 Items의 정렬 방법을 설정 (1줄)


## display

Flex Container를 정의한다.

값 | 의미 | 기본값
--- | --- | ---
flex | Block 특성의 Flex Container를 정의 |
inline-flex | Inline 특성의 Flex Container를 정의 |


## flex-flow

Flex Itemsd의 주 축을 설정하고 Items의 여러 줄 묶음(줄 바꿈)도 설정한다. `단축`

```css
flex-flow: 주축 여러줄묶음;
```

```css
.flex-container {
    flex-flow: row-reverse wrap;
}
```

값 | 의미 | 기본값
--- | --- | ---
flex-direction | Items의 주 축을 설정 | row
flex-wrap | Items의 여러 줄 묶음(줄 바꿈) 설정 | nowrap


### flex-direction

Items의 주 축을 설정한다.

값 | 의미 | 기본값
--- | --- | ---
row | Items를 수평축으로 표시 | row
row-reverse | Items를 row의 반대 축으로 표시 | 
column | Items를 수직축으로 표시 | 
row-reverse | Items를 column의 반대 축으로 표시 | 

<img width="386" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134623025-27e384cb-745f-4e5f-b1bd-04d670f8cd28.PNG">


### 주 축과 교차 축

값 row는 Items를 수평축으로 표시하므로 이때 주 축은 수평이며 교차 축은 수직이다.  
반대로 값 column은 Items를 수직축으로 표시하므로 주 축은 수직이며 교차 축은 수평이 된다.