# 멀티미디어 & 내장 콘텐츠 & 스크립트 (21/09/07)

## 멀티미디어

### `<img />`

이미지를 삽입

속성 | 의미 | 값 | 특징
--- | --- | ---| ---
src | (필수)이미지 URL
alt | (필수)이미지의 대체 텍스트
width | 이미지의 가로 너비 | |
height | 이미지의 세로 너비 | |
srcset | 브라우저에게 제시할 이미지 URL과 원본 크기의 목록을 정의 | w, x |
sizes | 미디어 조건과 해당 조건일 때 이미지 최적화 크기의 목록을 정의 | |

```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  src="images/heropy.png"
  alt="HEROPY" />
```

width를 설정한 경우에는 최적화된 사이즈에서 width의 사이즈를 가진 이미지가 출력된다.

```html
<img
  srcset="images/heropy_small.png 1x,
          images/heropy_medium.png 1.75x,
          images/heropy_large.png 2.5x"
  src="images/heropy.png"
  alt="HEROPY" />
```

400w를 1x 기준으로 삼는다.<br>
일반적으로 w 단위를 사용하면 된다.

```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  sizes="(min-width: 1000px) 700px"
  src="images/heropy.png"
  alt="HEROPY" />
```

위 예제의 결과로,<br>
뷰포트 너비가 400px 이하일 때 `heropy_small.png`(400px)가 사용된다.<br>
뷰포트 너비가 401~700px 일 때 `heropy_medium.png`(700px)가 사용된다.<br>
뷰포트 너비가 701~999px 일 때 `heropy_large.png`(1000px)가 사용된다.<br>
뷰포트 너비가 1000px 이상일 때 `heropy_medium.png`(700px)가 사용된다.<br>

```html
<img
  srcset="images/heropy_small.png 400w,
          images/heropy_medium.png 700w,
          images/heropy_large.png 1000w"
  sizes="500px"
  src="images/heropy.png"
  alt="HEROPY" />
```

medium img가 나오고 크기는 500px이다.<br>
500px에서 최적화된 이미지는 medium이기 때문이다.
<br>
srcset과 sizes는 IE에서 지원하지 않는다.
[참고자료](https://heropy.blog/2019/06/16/html-img-srcset-and-sizes/)

### `<audio>`

소리 콘텐츠(MP3)를 삽입.

속성 | 의미 | 값 | 기본값
--- | --- | ---| ---
autoplay | 준비되면 바로 재생 | boolean | 
controls | 제어 메뉴를 표시 | boolean |
loop | 재생이 끝나면 다시 처음부터 재생 | boolean |
preload | 페이지가 로드될 때 파일을 로드할지의 지정 | none: 로드하지 않음<br> metadata: 메타데이터만 로드.<br> auto: 전체 파일 로드 | metadate
src | 콘텐츠 URL | URL |
muted | 음소거 여부 | boolean |