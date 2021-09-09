# 표 콘텐츠 & 양식 (21/09/09)

## 표 콘텐츠

### `<table>, <tr>, <th>, <td>`

데이터 표( `<table>` )의 행(줄 / `<tr>`)과 열(칸, 셸(Cell) / `<th>`, `<td>`)을 생성.<br>
(Table Row, Table Header, Table Data)

```css
table { display: table; }
tr { display: table-row; }
th, td { display: table-cell; }
```

### `<th>`

'머리글 칸'을 지정

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
abbr | 열에 대한 간단한 설명 | |
headers | 관련된 하나 이상의 다른 머리글 칸 `id` 속성값 | |
colspan | 확장하려는(병합) 열의 수 | | 1
rowspan | 확장하려는(병합) 행의 수 | | 1
scope | 자신이 누구의 머리글 칸 인지 명시 | col : 자신의 열<br>colgroup : 모든 열<br>row : 자신의 행<br>rowgroup : 모든 행<br>auto | auto


### `<td>`

일반 칸을 지정

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
headers | 관련된 하나 이상의 다른 머리글 칸 `id` 속성값 | |
colspan | 확장하려는(병합) 열의 수 | | 1
rowspan | 확장하려는(병합) 행의 수 | | 1


### `<caption>`

표의 제목을 설정.

- 열리는 TABLE 태그 바로 다음에 작성해야 함.
- `<table>` 당 하나의 `<caption>`만 사용 가능.

```css
caption { display: table-caption; }
```


### `<colgroup>, <col>`

표의 열들을 공통적으로 정의하는 컬럼(`<col>`)과 그의 집합(`<colgroup>`)

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
span | 연속되는 열 수 | 숫자 | 1


```css
colgroup { display: table-column-group; }
col { display: table-column; }
```


### `<thead>, <tbody>, <tfoot>`

표의 머리글, 본문, 바닥글을 지정.

- 기본적으로 테이블의 레이아웃에 영향을 주지 않음.

```css
<table>
  <caption>Fruits</caption>
  <colgroup>
    <col span="2" style="background-color: yellowgreen;">
    <col style="background-color: tomato;">
  </colgroup>
  <thead>
    <tr>
      <th>ID</th>
      <th>Name</th>
      <th>Price</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>F123A</td>
      <td>Apple</td>
      <td>$22</td>
    </tr>
    <tr>
      <td>F098B</td>
      <td>Banana</td>
      <td>$19</td>
    </tr>
  </tbody>
</table>
```

## 양식

### `<form>`

웹 서버에 정보를 제출하기 위한 양식 범위를 정의.

- `<form>`이 다른 `<form>`을 자식 요소로 포함할 수 없음.

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
action | 전송한 정보를 처리할 웹페이지의 URL | URL |
autocomplete | 사용자가 이전에 입력한 값으로 자동 완성 기능을 사용할 것인지 여부 | on, off | on
method | 서버로 전송할 HTTP 방식 | GET, POST | GET
name | 고유한 양식의 이름 | |
novalidate | 서버로 전송 시 양식 데이터의 유효성을 검사하지 않도록 지정 | |
target | 서버로 전송 후 응답받을 방식을 지정 | _self, _blank | _self

GET 방식은 URL에 정보가 보여서 전송됨
POST 방식은 Form Data에 숨겨진다. 의도한 경우에는 노출 가능

```css
form { display : block;}
```


### `<input />`

사용자에게 입력 받을 데이터 양식.

속성 | 의미 | 값 | 기본값 | 특징
--- | --- | --- | --- | ---
autocomplete | 사용자가 이전에 입력한 값으로 자동완성 기능 | on, off | on | 
autofocus | 페이지가 로드될 때 자동으로 포커스 | boolean | | 문서 내 고유해야 함
form | `<form>`의 id 속성 값 | | 해당 `<form>`의 후손이 아닐 경우만
name | 양식의 이름 | | |
**type** | 입력 받을 데이터의 종류 | 별도 정리 | text |

### 데이터 종류(TYPE)의 값(Values)

type 속성에 입력할 수 있는 값의 목록.

```html
<input type="button" />
```

값 | 데이터 종류 | 특징
--- | --- | ---
button | 일반 버튼 | `<button>`처럼 사용
checkbox | 체크박스 |
email | 이메일 |
file | 파일 |
password | 비밀번호 | 가려지는 양식
submit | 제출 버튼 |해당 `<form>`범위 내 고유한 양식
text | 일반 텍스트 | 


### `<label>`

라벨 가능 요소의 제목

- for 속성으로 라벨 가능 요소를 참조하거나 콘텐츠로 포함.
- 라벨 가능 요소: `<button>, <input>, <progress>, <select>, <textarea>`

속성 | 의미
--- | --- 
for | 참조할 라벨 가능 요소의 id 속성 값

```html
<!-- 라벨 가능 요소를 참조 -->
    <input type="checkbox" id="user-agreement" />
    <label for="user-agreement">동의하십니까?</label>
    <!-- label의 제목이 input의 제목임을 알기위해 for사용 -->

    <!-- 라벨 가능 요소를 포함 (보통 이렇게 사용)-->
    <label><input type="checkbox" />동의하십니까?</label>
```


### `<button>`

선택 가능한 버튼을 지정

속성 | 의미 | 값 | 특징
--- | --- | --- | ---
autofocus | 페이지가 로드될 때 자동으로 포커스 | boolean | 문서 내 고유해야 함
disabled | 버튼을 비활성화 | boolean |
form | `<form>`의 id 속성 값 | | 해당 `<form>`의 후손이 아닐 경우만
name | 폼 데이터와 함께 전송되는 버튼의 이름 | |
type | 버튼의 타입 | `button, reset, submit` |


### `<textarea>`

여러 줄의 일반 텍스트 양식

속성 | 의미 | 값 | 기본값 | 특징
--- | --- | --- | --- | ---
autocomplete | 사용자가 이전에 입력한 값으로 자동완성 기능 | on, off | on | 
autofocus | 페이지가 로드될 때 자동으로 포커스 | boolean | | 문서 내 고유해야 함
form | `<form>`의 id 속성 값 | | 해당 `<form>`의 후손이 아닐 경우만
name | 양식의 이름 | | |
placeholder | 사용자가 입력할 값의 힌트 | | |
readonly | 수정 불가한 읽기 전용 | boolean | |
rows | 양식의 줄 수 | 숫자 | 2 |


### `<fieldset>, <legend>`

같은 목적의 양식을 그룹화(fieldset) 하여 제목 (legend)을 지정.

```html
<form>
  <fieldset>
    <legend>Coffee Size</legend>
    <label>
        <input type="radio" name="size" value="tall" />
        Tall
    </label>
    <label>
        <input type="radio" name="size" value="grande" />
        Grande
    </label>
    <label>
        <input type="radio" name="size" value="venti" />
        Venti
    </label>
  </fieldset>
</form>
```

속성 | 의미 | 값
--- | --- | ---
disabled | 그룹 내 모든 양식 요소를 비활성화 | boolean
form | 그룹이 속할 하나 이상의 `<form>`의 id 속성 값 |
name | 그룹의 이름


### `<select>, <datalist>, <optgroup>, <option>`

옵션(`<option>, <optgroup>`)의 선택 메뉴(`<select>`)나 자동완성(`<datalist>`)을 제공.

1. `<select>`

옵션을 선택하는 메뉴

속성 | 의미 | 값 | 기본값
--- | --- | --- | ---
autocomplete | 사용자가 이전에 입력한 값으로 자동완성 기능 | on, off | on 
disabled | 그룹 내 모든 양식 요소를 비활성화 | boolean | 
form | 그룹이 속할 하나 이상의 `<form>`의 id 속성 값 | |
multiple | 다중 선택 여부 | boolean |
name | 선택 메뉴의 이름 | |
size | 한 번에 볼 수 있는 행의 개수 | 숫자 | 0(1과 같음)

1. `<optgroup>`

`<option>`을 그룹화

속성 | 의미 | 값
--- | --- | ---
label | (필수) 옵션 그룹의 이름 |
disabled | 옵션 그을 비활성화 | boolean

1. `<option>`

선택 메뉴(`<select>`)나 자동완성(`<datalist>`)에서 사용될 옵션.

- 선택적 빈 태그로 사용 가능.

속성 | 의미 | 값 | 특성
--- | --- | --- | ---
disabled | 옵션 그을 비활성화 | boolean |
label | 표시될 옵션의 제목 | | 생략되면 포함된 텍스트를 표시
selected | 옵션이 선택되었음을 표시 | boolean |
value | 양식으로 제출될 값 | | 생략되면 포함된 텍스트를 값으로 사용

1. `<datalist>`

`<input>`에 미리 정의된 옵션을 지정하여 자동완성 기능을 제공하는 데 사용

- `<input>`의 list 속성 바인딩
- `<option>`을 포함하여 정의된 옵션을 지정

```html
<input type="text" list="fruits">

<datalist id="fruits">
  <option>Apple</option>
  <option>Orange</option>
  <option>Banana</option>
  <option>Mango</option>
  <option>Fineapple</option>
</datalist>
```


### `<progress>`

작업의 완료 진행률을 표시

속성 | 의미 | 값 | 특성
--- | --- | --- | ---
max | 작업의 총량 | 숫자 |
value | 작업의 진행량 | 숫자 | `max`: 속성을 생략할 경우 `0 ~ 1` 사이의 숫자여야 함
