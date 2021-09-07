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


### `<video>`

동영상 콘텐츠(MP4)를 삽입.

- autoplay가 지정된 경우, preload는 무시됨.

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
autoplay | 준비되면 바로 재생 | boolean |
controls | 제어 메뉴를 표시 | boolean |
crossorigin | 가져오기가 `CORS`를 사용하여 수행되어야 하는지 여부 | anonymous, use-credentials |
loop | 재생이 끝나면 다시 처음부터 재생 | boolean |
muted | 음소거 여부 | boolean |
poster | 동영상 썸네일 이미지 URL | URL |
preload | 페이지가 로드될 때 파일을 로드할지의 지정(힌트 제공) | none: 로드하지 않음<br> metadata: 메타데이터만 로드.<br> auto: 전체 파일 로드 | metadata
src | 콘텐츠 URL | URL |
width | 동영상 가로 너비 | |
height | 동영상 세로 너비 | |

```css
video { display: inline; }
```


### `<figure>, <figcaption>`

`<figure>`는 이미지나 삽화, 도표 등의 영역을 설정.<br>
`<figcaption>`는 `<figure>`에 포함되어 이미지나 삽화 등의 설명을 표시.

```html
<figure>
  <img src="milk.jpg" alt="A milk">
  <figcaption>Milk is a nutrient-rich, white liquid food produced by the mammary glands of mammals.</figcaption>
</figure>
```

```css
figure { display: block; }
figcaption { display: inline; }
```


### `<iframe>`

다른 HTML 페이지를 현재 페이지에 삽입. <br>
(중첩된 브라우저 컨텍스트(프레임)를 표시)

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
name | 프레임의 이름 | |
src | 포함할 문서의 URL | URL |
width | 프레임의 가로 너비 | |
height | 프레임의 세로 너비 | |
allowfullscreen | 전체 화면 모드 사용 여부 | boolean |
frameborder | 프레임 테두리 사용 여부 | 0, 1 | 1
sandbox | 보안을 위한 읽기 전용으로 삽입 | boolean or<br> allow-form: 양식 제출 가능,<br> allow-scripts: 스크립트 실행 가능,<br> allow-same-origin: 같은 출저의 리소스 사용 가능 | |



### `<canvas>`

`Canvas API`이나 `WebGL API`를 사용하여 그래픽이나 애니메이션을 렌더링.

속성 | 의미
--- | ---
width | 캔버스의 가로 너비
heigth | 캔버스의 세로 너비

```css
canvas { display: inline; }
```


### `<script>`

스크립트 코드를 문서에 포함 or 참조(외부 스크립트)

속성 | 의미 | 값 | 기본값 | 특징
--- | --- | --- | --- | --- |
async | 스크립트의 비동기적 실행 여부 | boolean | | src 속성 필수
crossorigin | 별도의 도메인을 사용하는 사이트의 오류 로깅을 허용하기 위해 사용 | anonymous, user-credentials | |
defer | 문서 파싱(구문 분석) 후 작동 여부 | boolean | | src 속성 필수
src | 참조할 외부 스크립트 URL | URL | | 포함된 스크립트 내부 코드는 무시됨
type | MIME 타입 | | `text/javascript` |


동기적 실행은 위에서 아래로 순서대로 실행<br>
비동기적 실행은 필요에 의해서 순서를 건너뛰고 실행


### `<noscript>`

스크립트를 지원하지 않는 경우에 삽입할 HTML을 정의.

```html

```

