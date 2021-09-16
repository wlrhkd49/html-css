# 글꼴, 문자 (21/09/15 ~ 21/09/16)

## font

글자 관련 속성들을 지정 `단축`

값 | 의미 | 기본값
--- | --- | ---
font-style | 글자 기울기 지정 | normal
font-weight | 글자 두께 지정 | normal
font-size | 글자 크기 지정 | medium( 16px )
line-height | 줄 높이(줄 간격) 지정 | normal(Reset.css 적용시 1)
font-family | 글꼴(서체) 지정 | 운영체제(브라우저)에 따라 달라짐

```css
font: 기울기 두께 크기 / 줄높이 글꼴;
```

```css
.box {
    font: italic bold 20px / 1.5 "Arial", sans-serif;
}
```

```css
.box {
    font: 10px / 1.5; /* ERROR */
    font: bold; /* ERROR */
    font: bold sans-serif; /* ERROR */
    font: 30px / 1.5 sans-serif;
    font: bold 30px sans-serif;
    font: italic 30px / 1.5 "Arial", sans-serif;
}
```

**단축 속성을 사용하려면 font-size와 font-family 필수 입력!!!**


1. font-style

글자 스타일(기울기)을 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
normal | 스타일 없음 | normal
italic | 이텔릭체 |
oblique | 기울어진 글자 |


2. font-weight

글자의 두께(가중치)를 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
normal | 기본 글자 두께, 400과 동일 | normal(400)
bold | 글자 두껍게, 700과 동일 |
bolder | 부모 요소보다 더 두껍게 |
lighter | 부모 요소보다 더 얇게 |
숫자 | 100부터 900까지의 100단위 숫자 9개, normal과 bold이외<br>의 두께를 제공하는 글꼴(서체)을 위한 설정


3. font-size

글자의 크기를 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
단위 | px, em, cm 등 단위로 지정 | 16px
% | 부모 요소의 비율로 지정 | 


4. line-height

줄 높이(줄 간격)을 지정 `개별`

값 | 의미 | 기본값
--- | --- | ---
normal | 브라우저의 기본 정의를 사용 | normal
숫자 | 요소 자체 글꼴 크기의 배수로 지정 |
단위 | px, em, cm 등 단위로 지정 |
% | 요소 자체 글꼴 크기의 비율로 지정 |


5. font-family

글꼴 (서체) 지정

값 | 의미 | 기본값
--- | --- | ---
글꼴이름 | 글꼴(서체), 후보 목록을 지정 |
serif | 글꼴 계열 이름을 지정 |
sans-serif | |
monospace | |
cursive | |
fantasy | |

```css
font-family: [글꼴 후보1, 글꼴 후보2...], 글꼴 계열;
```

```css
.box {
    font-family: Arial, "Open Sans", "돋움", dotum, sans-serif;
}
```

글꼴 후보를 정하는 이유는 브라우저로부터 사용자가 폰트를 다운받을 때 폰트의 용량이 크므로 사용자 폰트 중에서 찾아 쓰면 좋을 것 같기 때문에<br>

**글꼴 계열**

계열 | 의미 
--- | ---
serif | 바탕체 계열
sans-serif | 고딕체 계열
monospace | 고정너비(가로폭이 동등한) 글꼴 계열
cursive | 필기체 계열
fantasy | 장식 글꼴 계열


## color

문자의 색상을 지정

값 | 의미 | 기본값
--- | --- | ---
색상 | 문자의 색상을 지정 | rgb(0, 0, 0)

**색상 표현**
표현 | 의미 | 예시
--- | --- | ---
색상이름 | 브라우저에서 제공하는 색상의 이름 | red, blue
Hex 색상코드 | 16 진수 색상 | #000000 (대부분)
RGB | 빛의 삼원색 | rgb(255, 255, 255)
RGBA | 빛의 삼원색, 투명도 | rgba(255, 0, 0, .5)
HSL | 색상, 채도, 명도 | hsl(120, 100%, 50%)
HSLA | 색상, 채도, 명도, 투명도 | hsl(120, 100%, 50%, .3)


## text-align

문자 정렬 방식을 지정
값 | 의미 | 기본값
--- | --- | ---
left | 왼쪽 정렬 |
right | 오른쪽 정렬 |
center | 가운데 정렬 |
justify | 양쪽 맞춤 |

justify는 양쪽을 맞추고 띄어쓰기 간격 조절<br>
2줄 이상부터 동작


## text-decoration

문자의 장식(line)을 설정

값 | 의미 | 기본값
--- | --- | ---
none | 선 없음 | none
underline | 밑줄을 지정 | 
overline | 윗줄을 지정 | 
line-through | 중앙 선(가로지르는)을 지정 | 


## text-indent

(첫번째 줄의) 들여쓰기를 지정<br>
음수 값 사용 가능<br>
음수 값을 사용하면 첫째 줄은 왼쪽으로 들여쓰기 된다.


## letter-spacing

문자의 자간(글자 사이 간격)을 설정

값 | 의미 | 기본값
--- | --- | ---
normal | 단어 사이의 일반 간격 | normal
단위 | px, em, cm 등 단위로 지정 |


## word-spacing

단어 사이(띄어쓰기)의 간격을 설정

값 | 의미 | 기본값
--- | --- | ---
normal | 단어 사이의 일반 간격 | normal
단위 | px, em, cm 등 단위로 지정 |