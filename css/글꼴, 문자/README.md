# 글꼴, 문자 (21/09/15)

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