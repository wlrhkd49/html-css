# 전역 속성, 기타 (21/09/11)

## 전역 속성 (Global Attribures)

모든 HTML 요소에서 공통적으로 사용 가능한 속성.

### class (별명)

공백으로 구분된 요소의 별칭을 지정.<br>
CSS혹은 JavaScript의 요소 선택기를 통해서 요소를 선택하거나 접근


### id (이름 (고유))

문서에 고유한 식별자를 정의. <br>
CSS혹은 JavaScript의 요소 선택기를 통해서 요소를 선택하거나 접근


### style (전역 , css 인라인)

요소에 적용할 CSS를 선언.


### title

요소의 정보(설명)을 지정.


### lang

요소의 언어를 지정. 보통 html에서 처음 선언

```html
<p lang="en">This paragraph is English</p>
<p lang="ko">이 단락은 한글입니다.</p>
<p lang="fr">Ce paragraphe est défini en français.</p>
```


### data-*

사용자 정의 데이터 속성을 지정.<br>
HTML에 JavaScript에서 이용할 수 있는 데이터(정보)를 저장하는 용도로 사용.

```html
<!-- data-custom-data-attributes -->
<div id="me" data-my-name="Heropy" data-my-age="851">Heropy</div>
```

```js
// dataset.customDataAttributes
const $me = document.getElementById('me');
console.log($me.dataset.myName); // "Heropy"
console.log($me.dataset.myAge); // "851"
```


### draggable

요소가 Drag and Drop API를 사용 가능한지 여부를 지정.<br>
작성하지 않은 경우에는 auto로 브라우저가 판단

```html
<div draggable="true">The element to drag.</div>
```


### hidden

요소를 숨김.

```html
<form id="hidden-form" action="/form-action" hidden>
  <!-- 숨겨진 양식들.. -->
</form>
<button form="hidden-form" type="submit">전송</button>
```


### tabindex

Tab키를 이용해 요소를 순차적으로 포커스 탐색할 순서를 지정.

- 대화형 콘텐츠(`<a>, <button>, <img>, <video>`)는 기본적으로 코드 순서대로 탭 순서가 지정됨.
- 비대화형 콘텐츠에 tabindex="0"을 지정하여 대화형 콘텐츠와 같이 탭 순서를 사용.
- tabindex="-1"을 통해 포커스는 가능하지만 탭 순서에서 제외 가능.
- tabindex="1"이상의 양수 값은 논리적 흐름을 방해하기 때문에 사용을 추천하지 않음

```html
<h1 tabindex="0">Sign In</h1>
<label>Username: <input type="text"></label>
<label>Password: <input type="password"></label>
<label>PS: <input type="text" tabindex="-1"></label>
<input type="submit" value="Sign In">
```