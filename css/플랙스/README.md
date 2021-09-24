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


### 시작점(flex-start)과 끝점(flex-end)

주 축이나 교차 축의 시작하는 지점과 끝나는 지점을 지칭한다.  
방향에 따라 시작점과 끝점이 달라진다.


## flex-wrap

Items의 여러 줄 묶음(줄 바꿈)을 설정한다.

값 | 의미 | 기본값
--- | --- | ---
nowrap | 모든 Items를 여러 줄로 묶지 않음(한 줄에 표시) | nowrap
wrap | Items를 여러 줄로 묶음 |
wrap-reverse | Items를 wrap의 역 방향으로 여러 줄로 묶음 | 

```css
flex-wrap: 여러줄묶음;
```

기본적으로 Items는 한 줄에서만표시되고 줄 바꿈 되지는 않는다.  

<img width="295" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134680857-ca3e03e5-5e94-4878-bcd2-b34334b408b0.PNG">


## justify-content

주 축의 정렬 방법을 설정한다.

값 | 의미 | 기본값
--- | --- | ---
flex-start | Items를 시작점으로 정렬 | flex-start
flex-end | Items를 끝점으로 정렬 |
center | Items를 가운데 정렬 |
space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |
space-around | Items를 균등한 여백을 포함하여 정렬 |


```css
justify-content: 정렬방법;
```

<img width="296" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134681955-c65b33ec-ea02-4fa2-9205-1901226bb9ab.PNG">


## align-content

교차 축의 정렬 방법을 설정한다.  
주의할 점은 flex-wrap 속성을 통해 Items가 여러 줄(2줄 이상)이고 여백이 있을 경우만 사용할 수 있다.

> Items가 한 줄일 경우 align-items 속성을 사용

값 | 의미 | 기본값
--- | --- | ---
stretch | Container의 교차 축을 채우기 위해 Items를 늘림 | stretch
flex-start | Items를 시작점으로 정렬 | flex-start
flex-end | Items를 끝점으로 정렬 |
center | Items를 가운데 정렬 |
space-between | 시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨 |
space-around | Items를 균등한 여백을 포함하여 정렬 |

<img width="427" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134682954-62c34bcf-b003-4b4c-9d06-454688683371.PNG">


## align-items

교차 축에서 정렬 방법을 설정한다.  
Items가 한 줄일 경우 많이 사용한다.  
<br>
주의할 점은 Items가 flex-wrap을 통해 여러 줄일 경우에는 align-content 속성이 우선한다.  
따라서 align-items를 사용하려면 align-content 속성을 기본값(stretch)으로 설정해야한다.

값 | 의미 | 기본값
--- | --- | ---
stretch | Container의 교차 축을 채우기 위해 Items를 늘림 | stretch
flex-start | Items를 각 줄의 시작점으로 정렬 |
flex-end | Items를 각 줄의 끝점으로 정렬 |
center | Items를 가운데 정렬 |
baseline | Items를 문자 기준선에 정렬 |

<img width="435" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134684425-55176e37-e2ee-407a-8cd8-2e82fbd31ed8.PNG">


## Flex Items

Flex Items를 위한 속성들은 다음과 같다.

속성 | 의미 
--- | ---
order | Flex Item의 순서를 설정
flex | flex-grow, flex-shrink, flex-basis의 단축 속성
flex-grow | Flex-Item의 증가 너비 비율을 설정
flex-shrink | Flex-Item의 감소 너비 비율을 설정
flex-basis | Flex-Item의 (공간 배분 전) 기본 너비 설정
align-self | 교차 축에서 Item의 정렬 방법을 설정
<br>

## order

Item의 순서를 설정한다.  
Item에 숫자를 지정하고 숫자가 클수록 순서가 밀린다.  
음수가 허용된다.  

> HTML 구조와 상관없이 순서를 변경할 수 있기 때문에 유용하다.

값 | 의미 | 기본값
--- | --- | ---
숫자 | Item의 순서를 설정 | 0

```css
order: 순서;
```

<img width="289" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134686360-9a1ece7f-afc4-411b-9bc1-0b83eb0950ce.PNG">


## flex-grow

Item의 증가 너비 비율을 설정한다.  
숫자가 크면 더 많은 너비를 가진다.  
Item이 가변 너비가 아니거나, 값이 0일 경우 효과가 없다.  

값 | 의미 | 기본값
--- | --- | ---
숫자 | Item의 증가 너비 비율을 설정 | 0

```css
flex-grow: 순서;
```

모든 Items의 총 증가 너비(flex-grow)에서 각 Item의 증가 너비의 비율 만큼 너비를 가질 수 있습니다.  
예를 들어 Item이 3개이고 증가 너비가 각각 1, 2, 1이라면,  
첫 번째 Item은 총 너비의 25%(1/4)을,  
두 번째 Item은 총 너비의 50%(2/4)를,  
세 번째 Item은 총 너비의 25%(1/4)을 가지게 됩니다.  

<img width="321" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134688199-8755105f-7d48-4a63-9d33-18d98959b7d9.PNG">


## flex-shrink

Item이 감소하는 너비의 비율을 설정한다.  
숫자가 크면 더 많은 너비가 감소한다.  
Item이 가변 너비가 아니거나, 값이 0일 경우 효과가 없다.

값 | 의미 | 기본값
--- | --- | ---
숫자 | Item의 감소 너비 비율을 설정 | 1

```css
flex-shrink: 순서;
```

<img width="425" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134690477-33cf47ef-5cb4-470b-9357-e3efbbbd3a9b.PNG">


## flex-basis

Item의 (공간 배분 전) 기본 너비를 설정한다.  
값이 auto일 경우 width, height 등의 속성으로 Item의 너비를 설정할 수 있다.  
하지만 단위 값이 주어질 경우 설정할 수 없다.  

값 | 의미 | 기본값
--- | --- | ---
auto | 가변 Item과 같은 너비 | auto
단위 | px, em, cm 등 단위로 지정

```css
flex-basis: 기본너비;
```

flex 속성에서 설명한 것 같이 단축 속성 내에서 flex-basis를 생략하면 값이 0이 되는 것을 주의  

<img width="418" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134691404-4d724dff-288f-44b5-86b6-8a6aa8dedf12.PNG">


## flex

Item의 너비(증가, 감소, 기본)를 설정하는 단축 속성이다.

값 | 의미 | 기본값
--- | --- | ---
flex-grow | Item의 증가 너비 비율을 설정 | 0
flex-shrink | Item의 감소 너비 비율을 설정 | 1
flex-basis | Item의 (공간 배분 전) 기본 너비 설정 | auto

```css
flex: 증가너비 감소너비 기본너비;
```

```css
.item {
    flex: 1 1 20px; /* 증가너비 감소너비 기본너비 */
    flex: 1 1; /* 증가너비 감소너비 */
    flex: 1 20px; /* 증가너비 기본너비 (단위를 사용하면 flex-basis가 적용 */
}
```

> flex: 1; 을 하면 flex-basis가 auto가 아닌 0으로 설정된다!


## align-self

교차 축에서 개별 Item의 정렬 방법을 설정한다.

align-item는 Container 내 모든 Items의 정렬 방법을 설정한다.  
필요에 의해 일부 Item만 정렬 방법을 변경하려고 할 경우 align-self를 사용할 수 있다.  
이 속성은 align-items 속성보다 우선한다.  

값 | 의미 | 기본값
--- | --- | ---
auto | Container의 align-items 속성을 상속 받음 | auto
stretch | Container의 교차 축을 채우기 위해 Items를 늘림 | 
flex-start | Items를 각 줄의 시작점으로 정렬 | 
flex-end | Items를 각 줄의 끝점으로 정렬 |
center | Items를 가운데 정렬 |
baseline | Items를 문자 기준선에 정렬 |

<img width="297" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134693963-64a18823-1fd8-42b3-9e96-f9e004d9dd5c.PNG">

