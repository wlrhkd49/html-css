# 인라인 텍스트 & 수정 (21/09/03)

## `<a>`

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

## `<abbr>`

약어를 지정한다.<br>
(Abbreviation 보통 `title`속성을 사용하여 전체 글자나 설명을 제공)

```css
  Using <abbr title="HyperText Markup Language">HTML</addr> is fun and easy!
```

```css
  abbr { display: inline; }
```