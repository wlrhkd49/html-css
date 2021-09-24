# animation

요소에 애니메이션을 설정/제어 `단축`

값 | 의미 | 기본값
--- | --- | ---
animation-name | @keyframes 규칙의 이름을 지정 | none
animation-duration | 애니메이션의 지속 시간 설정 | 0s
animation-timing-function | 타이밍 함수 지정 | ease
animation-delay | 애니메이션의 대기 시간 설정 | 0s
animation-iteration-count | 애니메이션의 반복 횟수 설정 | 1
animation-direction | 애니메이션의 반복 방향 설정 | normal
animation-fill-mode | 애니메이션의 전후 상태(위치) 설정 | none
animation-play-state | 애니메이션의 재생과 정지 설정 | running

```css
animation: 애니메이션이름 지속시간 [타이밍함수 대기시간 반복횟수 반복방향 전후상태 재생/정지];
```

```css
.box {
    width: 100px;
    height: 100px;
    background: tomato;
    animation: hello 2s linear infinite both;
}

@keyframes hello {
    0% { width: 200px; }
    100% { width: 50px; }
}
```

## `@keyframes`

2개 이상의 애니메이션 중간 상태(프레임)을 지정

```css
@keyframes 애니메이션이름 {
    0% {속성: 값;}
    50% {속성: 값;}
    100% {속성: 값;}
}
```

## animation-name

`@keyframes` 규칙(애니메이션 프레임)의 이름을 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
none | 애니메이션을 지정하지 않음 | none
`@keyframes` | 이름이 일치하는 `@keyframes` 규칙의 애니메이션을 적용 |


## animation-duration

애니메이션의 지속 시간 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
시간 | 지속 시간을 설정 | 0s


## animation-timing-function

타이밍 함수(애니메이션 효과를 계산하는 방법) 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
ease | 빠르게-느리게 | ease
linear | 일정하게 |
ease-in | 느리게-빠르게 |
cubic-bezier(n,n,n,n) | 자신만의 값을 정의 (0~1) |
steps(n) | n번 분할된 애니메이션 |


## animation-delay

애니메이션의 대기 시간 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
시간 | 대기 시간을 설정 | 0s

> 음수가 허용됩니다. 음수가 있을 경우 애니메이션은 바로 시작되지만, 그 값만큼 애니메이션이 앞서 시작합니다(애니메이션 주기 도중에 시작)


## animation-iteration-count

애니메이션의 반복 횟수를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
숫자 | 반복 횟수를 설정 | 1
infinite | 무한 반복 | 


## animation-direction

애니메이션 반복 방향을 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
normal | 정방향만 반복 | normal
reverse | 역방향만 반복 | 
alternate | 정방향에서 역방향으로 반복(왕복) |
alternate-reverse | 역방향에서 정방향으로 반복(왕복) |


## animation-fill-mode

애니메이션의 전후 상태(위치)를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
none | 기존 위치에서 시작 -><br> 애니메이션 시작 위치로 이동 -><br> 동작-><br> 기존 위치에서 끝 | none
forwards | 기존 위치에서 시작 -><br> 애니메이션 시작 위치로 이동 -><br> 동작-><br> 애니메이션 끝 위치에서 끝 | 
backwards | 애니메이션 시작 위치에서 시작 -><br> 동작-><br> 기존 위치에서 끝 | 
both | 애니메이션 시작 위치에서 시작 -><br> 동작-><br> 애니메이션 끝 위치에서 끝 | 


## animation-play-state

애니메이션의 재생과 정지를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
running | 애니메이션을 동작 | runnning
paused | 애니메이션 동작을 정지 |


# 다단 (Multi-Columns)

일반 블록 레이아웃을 확장하여<br>
여러 텍스트 다단으로 쉽게 정리하며, 가독성 확보  

<img width="278" alt="캡처" src="https://user-images.githubusercontent.com/63788023/134619421-c56aae4b-ba88-43e8-8d5c-26485596e8a7.PNG">


## columns

다단을 정의 `단축`

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 단의 너비와 개수를 설정 | auto
column-width | 단의 최적 너비를 설정 | auto
auto | 단의 개수를 설정 | auto

```css
columns: 너비 개수;
```

```css
.text {
    columns: 100px 2;
}
```


## column-width

단의 최적 너비를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 단의 너비를 설정 | auto
단위 | px, em, cm 등 단위로 지정 |

```css
column-width: 너비;
```

> 각 단이 줄어들 수 있는 최적 너비(최소 너비)를 설정하며,<br>요소의 너비가 가변하여 하나의 단이(최적 너비)보다 줄어들 경우 단의 개수가 조정됩니다.


## column-count

단의 개수를 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
auto | 브라우저가 단의 너비를 설정 | auto
숫자 | 단의 개수를 설정 |

```css
column-count: 개수;
```

## column-gap

단과 단 사이의 간격 설정

값 | 의미 | 기본값
--- | --- | ---
normal | 브라우저가 단과 단 사이의 간격을 설정 | normal
단위 | px, em, cm 등 단위로 지정 |

```css
column-gap: 간격;
```


## column-rule

단과 단 사이의 (구분)선을 지정 `단축`

값 | 의미 | 기본값
--- | --- | ---
column-width | 선의 두께를 지정 | medium
column-style | 선의 종류를 지정 | none
column-color | 선의 색상을 지정 | 요소의 글자색과 동일

```css
column-rule: 두께 종류 색상;
```

> 단과 단 사이 중간에 위치한다.