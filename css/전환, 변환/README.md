# CSS / 속성 - 전환 & 변환 (21/09/23)

## Transitions

CSS 속성의 전환 효과를 지정

---

### transition

CSS 속성의 시작과 끝을 지정(전환 효과)하여 중간 값을 애니메이션 `단축`

값 | 의미 | 기본값
--- | --- | ---
transition-property | 전환 효과를 사용할 속성 이름 | all
transition-duration | 전환 효과의 지속시간 설정 | 0s
transition-timing-function | 타이밍 함수 지정(타이밍 함수란?) | ease
transition-delay | 전환 효과의 대기시간 설정 | 0s


1. trasition-property

전환 효과를 사용할 속성 이름을 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
all | 모든 속성에 적용 | all
속성이름 | 전환 효과를 사용할 속성 이름 |

2. transition-duration

전환 효과의 지속시간을 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
시간 | 전환 효과가 지속되는 시간 | 0s

3. transition-timing-function

타이밍 함수(애니메이션 전환 효과를 계산하는 방법) 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
ease | 빠르게-느리게 | ease
linear | 일정하게 |
ease-in | 느리게-빠르게 |
cubic-bezier(n,n,n,n) | 자신만의 값을 정의 (0~1) |
steps(n) | n번 분할된 애니메이션 |

4. transition-delay

전호나 효과가 몇 초 뒤에 시작할지 대기시간을 설정 `개별`

값 | 의미 | 기본값
--- | --- | ---
시간 | 전환 효과의 대기시간을 설정 | 0s


## transform

요소의 변환 효과(변형)을 지정

```css
transform: 변환함수1, 변환함수2, 변환함수3 ...;
transform: 원근법 이동 크기 회전 기울임;
```

```css
.box {
    transform: rotate(20deg) translate(10px, 0);
    /* 20도 각도 회전, 이동 x축 10px, y축 0px */
}
```

## transform 2D 변환 함수

값(변환함수) | 의미 | 단위
--- | --- | ---
translate(x, y) | 이동(X축, Y축) | 단위
translateX(x) | 이동(X축) | 단위
translateY(y) | 이동(Y축) | 단위
scale(x, y) | 크기(X축, Y축) | 없음(배수)
scaleX(x) | 크기(X축) | 없음(배수)
scaleY(y) | 크기(Y축) | 없음(배수)
rotate(degree) | 회전(각도) | deg
skew(x-deg, y-deg) | 기울임(X축, Y축) | deg
skewX(x-deg) | 기울임(X축) | deg
skewY(y-deg) | 기울임(Y축) | deg
matrix(n,n,n,n,n,n) | 2차원 변환 효과 | 없음

## transform 3D 변환 함수

값(변환함수) | 의미 | 단위
--- | --- | ---
translate3d(x, y, z) | 이동(X축, Y축, Z축) | 단위
translateZ(z) | 이동(Z축) | 단위
scale3d(x, y, z) | 크기(X축, Y축, Z축) | 없음(배수)
scaleZ(z) | 크기(Z축) | 없음(배수)
rotate3d(x, y, z, a) | 회전(X벡터, Y벡터, Z벡터, 각도) | 없음, deg
rotateX(x) | 회전(X축) | deg
rotateY(y) | 회전(Y축) | deg
rotateZ(z) | 회전(Z축) | deg
perspective(n) | 원근법(거리) | 단위
matrix3d(n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n,n) | 3차원 변환 효과 | 없음


## transfrom 변환 속성

속성 | 의미
--- | ---
transfrom-origin | 요소 변환의 기준점을 설정
transfrom-style | 3D 변환 요소의 자식 요소도 3D 변환ㅇ르 사용할지 설정
perspective | 하위 요소를 관찰하는 원근 거리를 설정
perspective-origin | 원근 거리의 기준점을 설정
backface-visibility | 3D 변환으로 회전된 요소의 뒷면 숨김을 설정

1. transform-origin

요소 변환의 기준점을 설정

값 | 의미 | 기본값
--- | --- | ---
X축 | left, right, center, %, 단위 | 50%
Y축 | top, bottom, center, %, 단위 | 50%
Z축 | 단위 | 0


2. transform-style

3D 변환 요소의 자식 요소도 3D 변환을 사용할지 설정

값 | 의미 | 기본값
--- | --- | ---
flat | 자식 요소의 3D 변환을 사용하지 않음 | flat
preserve-3d | 자식 요소의 3D 변환을 사용 |


## perspective

하위 요소를 관찰하는 원근 거리를 설정

값 | 의미 | 기본값
--- | --- | ---
단위 | px, em, cm 등 단위로 지정 |


## perspective 속성과 함수의 차이점

속성/함수 | 적용대상 | 기준점 설정
--- | --- | ---
perspective | 관찰 대상의 부모 요소 | perspective-origin
transform: perspective() | 관찰 대상 | transform-origin

> perspective 속성은 관찰 대상의 부모 요소에 적용하여 하위 요소들을 관찰하는 원근 거리를 설정하며, transform: perspective() 변환 함수는 관찰 대상에 직접 적용하여 그 대상을 관찰하는 원근 거리를 설정합니다.


## perspective-origin

원근 거리의 기준점을 설정

값 | 의미 | 기본값
--- | --- | ---
X축 | left, right, center, %, 단위 | 50%
Y축 | top, bottom, center, %, 단위 | 50%


## backface-visibility

3D 변환으로 회전된 요소의 뒷면 숨김을 설정

값 | 의미 | 기본값
--- | --- | ---
visible | 뒷면 숨기지 않음 | visible
hidden | 뒷면 숨김 |


## matrix(a,b,c,d,e,f)

요소의 2차원 변환 효과를 지정
scale(), skew(), translate(), rotate()를 지정

> 요소에 일반 변환 함수를 사용하더라도 브라우저에 의해 matrix함수로 계산되어 적용됩니다.(2D 변환 함수는 matrix로, 3D 변환 함수는 matrix3d로)<br> 따라서 일반적인 경우는 matrix 함수가 아닌 일반 변환 함수를 사용하면 됩니다.

