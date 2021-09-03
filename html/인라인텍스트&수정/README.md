# 인라인 텍스트 & 수정 (21/09/03)

## 인라인 텍스트

### `<a>`

다른 페이지, 같은 페이지 위치(`#`, 해시 태그), 파일, 이메일 주소, 전화번호 등 다른 URL로 연결할 수 있는 하이퍼링크를 설정.<br>
(Anchor, 외부로 내보내기)

- download: 이 요소가 리소스를 다운로드하는 용도로 사용됨을 의미

- href: 링크 URL  (생략 가능)

- ref: 현재 문서와 링크 URL의 관계

- target: 링크 URL의 표시(브라우저 탭) 위치<br> 
(_self 현재창에 띄움, _blank 새로운창을 만들고 띄움)

```css
  a { display: inline; }
```

### `<abbr>`

약어를 지정한다.<br>
(Abbreviation 보통 `title`속성을 사용하여 전체 글자나 설명을 제공)

```css
  Using <abbr title="HyperText Markup Language">HTML</addr> is fun and easy!
```

```css
  abbr { display: inline; }
```


### `<b>`

문체가 다른 글자의 범위를 설정.<br>
(Bring Attention)

- 특별한 의미를 가지지 않음.

- 읽기 흐름에 도움을 주는 용도로 사용.

- 다른 태그가 적합하지 않는 경우 마지막 수단으로 사용.

- 기본적으로 글자가 두껍게(Bold) 표시됨.

```css
  b { display: inline; }
```


### `<mark>`

사용자의 관심을 끌기 위한 하이라이팅할 때 사용. (의미 < 시각)

- 기본적으로 형광펜을 사용한 것처럼 글자 배경이 노란색으로 표시됨.

```css
  mark { display: inline; }
```


### `<em>`

단순한 의미 강조를 표시.<br>
(Emphasis)

- 중첩이 가능.

- 중첩될수록 강조 의미가 강해짐.

- 정보통신보조기기 등에서 구두 강조로 발음됨.

- 기본적으로 이텔릭체로 표시됨.

```css
  em { display: inline; }
```


### `<strong>`

의미의 중요성을 나타내기 위해 사용.

- 기본적으로 글자가 두껍게(Bold) 표시됨.

```css
  strong { display: inline; }
```


### `<i>`

`<em>, <strong>, <mark>, <cite>, <dfn>` 등에서 표현될 수 있는 적합한 의미가 아닌 경우 사용.<br>
(평범한 글자와 구분(아이콘이나 특수기호 같은)하기 위해 사용)

- 기본적으로 이텔릭체로 표시됨.

```css
  i { display: inline; }
```


### `<dfn>`

용어를 정의할 때 사용.<br>
(Definition)

- dt, dd, dl과 다르게 용어 하나만 있을 때 사용.

```css
  dfn { display: inline; }
```

### `<cite>`

창작물에 대한 참조를 설정.<br>
(책, 논문, 영화, TV 프로그램, 노래, 게임등의 제목)

- 기본적으로 이텔릭체로 표시됨.

```css
<cite>The Scream</cite> by Edward Munch. Painted in 1893.
```

```css
  cite { display: inline; }
```


### `<q>`

짧은 인용문을 설정.<br>
(Iinline Quotation)

- 긴 인용문을 설정할 경우 `<blockquote>` 사용

```css
  q { display: inline; }
```


### `<u>`

밑줄이 있는 글자를 설정.<br>
(Underline)

- 순수하게 꾸미는 용도의 요소로 사용.

- `<a>`와 헷갈릴 수 있는 위치에서 사용하지 않도록 주의.

- `<span style="text-decoration: underline;>`을 활용할 수 있는 경우에는 사용을 권장하지 않음.

```css
  u { display: inline; }
```


### `<code>`

컴퓨터 코드 범위를 설정.<br>
(Inline Code)

`<code>document.getElementById(`id-value`)</code> is a piece of computer code`

- 기본적으로 고정폭(가로 사이즈 동일) 글꼴 계열로 표시됨.

```css
  code { display: inline; }
```


### `<kbd>`

텍스트 입력 장치(키보드)에서 사용자 입력을 나타내는 텍스트 범위를 설정.

```css
<p><kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>K</kbd></p>, <kbd>ESC</kbd>
```

```css
  kbd { display: inline; }
```


### `<sup>, <sub>`

위 첨자`<sup>`와 아래 첨자`<sub>`를 설정.

```css
X<sup>4</sup> + Y<sup>2</sup> + H<sub>2</sub>O
```

```css
sup, sub { display: inline; }
```


### `<time>`

날짜와 시간을 나타내기 위한 목적으로 사용.

- Internet Explorer 에서 사용 불가능.

```css
<p>The Cure will be celebrating their 40th anniversary on <time datetime="2018-07-07">July 7</time> in London's Hyde Park.</p>
```


### `<span>`

본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정.

- div는 한 줄에 하나이므로 수직으로 쌓인다. 하지만 span은 수평으로 쌓인다. JS만 사용하는데는 span이 적합

```css
span { display: inline; }
```


### `<br />`

줄바꿈을 설정.

```css
br { display: inline; }
```


## 수정

### `<del>`

삭제된(변경된) 텍스트의 범위를 지정.

속성 | 의미 | 값 
--- | --- | ---
cite | 변경을 설명하는 리소스의 URI | URI
datetime | 변경이 일어난 유효한 날짜 문자 | DATE

```css
del { display: inline; }
```


### `<ins>`

새로 추가된(변경된) 텍스트의 범위를 지정.

속성 | 의미 | 값 
--- | --- | ---
cite | 변경을 설명하는 리소스의 URI | URI
datetime | 변경이 일어난 유효한 날짜 문자 | DATE

```css
ins { display: inline; }
```

