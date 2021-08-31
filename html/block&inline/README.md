# HTML - 블록 레벨(Block level)요소와 인라인(Inline) 요소 (21/08/31)
- 블록 요소

  1. DIV, H1, P
  
  1. 사용 가능한 최대 가로 너비를 사용한다.

  1. 크기를 지정할 수 있다.

  1. (width: 100%; height: 0;로 시작)

  1. 수직으로 쌓임

  1. margin, padding 위, 아래, 좌, 우 여백을 사용 가능하다.

  1. LAYOUT 잡을 때 사용


- 인라인 요소

  1. SPAN, IMG

  1. 필요한 만큼의 너비를 사용한다.

  1. 크기를 지정할 수 없다.

  1. (width: 0; height: 0;로 시작)

  1. 수평으로 쌓임

  1. margin, padding 위, 아래는 사용할 수 없다.

  1. TEXT 잡을 때 사용
  

- 블록, 인라인 요소의 default 값
  ```css
  div { display:block; }
  h1 { display:block; }
  p { display:block; }

  span { display:inline; }
  ```