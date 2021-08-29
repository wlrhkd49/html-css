# HTML
+ **HTML 문법 (21/08/29 ~ )**

  + HTML 기본문법
  
    + 태그는 각자의 의미를 가지고 있으며 다음과 같은 형태를 가집니다.
    
      <img width="339" alt="html" src="https://user-images.githubusercontent.com/63788023/131247289-52717ea1-8903-4e08-927c-090a6bb98ece.PNG">
      

    + 속성(Attributes)과 값(Value)
    
      <img width="402" alt="html" src="https://user-images.githubusercontent.com/63788023/131247437-0261e881-ccf7-4e9c-8c3c-9f56a8eb89ad.PNG">
      
      img처럼 닫히는 태그가 없으면 빈 태그(Empty Tag)라고 한다.

    + 부모와 자식 요소

      <img width="297" alt="html" src="https://user-images.githubusercontent.com/63788023/131247620-d70979a6-8c99-4c41-a985-4b411c1d6574.PNG">
    
      부모 자식 관계를 통해 요소들의 구성도를 파악할 수 있다.
      
    + 빈 태그
      : HTML에서 닫히는 개념이 없는 태그
    
      <img width="228" alt="html" src="https://user-images.githubusercontent.com/63788023/131247785-13218a9a-1dce-4bb9-8744-7ea2af51f789.PNG">
       
      빈 태그의 경우에는 거의 대부분 속성 = "값"의 형태가 붙는다
      
    + HTML 문서의 범위

      <img width="443" alt="html2" src="https://user-images.githubusercontent.com/63788023/131248075-41d51000-8216-4f3f-b36c-a115dd5e283f.PNG">
      
  + HTML 문서의 정보
  
    + TITLE(웹 페이지의 제목)
    
      HTML 문서의 제목을 정의한다.
      
        <img width="214" alt="html" src="https://user-images.githubusercontent.com/63788023/131248308-47a62e45-3296-4292-9733-70465e041126.PNG">
        
    + META(웹 페이지의 정보)
      
      HTML문서에 관한 정보 (표시방식, 제작자, 내용, 키워드 등)를 검색엔진이나 브라우저에 제공한다. (빈 태그)
      
        <img width="354" alt="html2" src="https://user-images.githubusercontent.com/63788023/131248338-0d03370a-b758-4ec4-a5da-be8dd6f294cb.PNG">
        
    + LINK(CSS 불러오기)
      
      외부 문서를 연결할 때 사용한다. (외부에서 작성된 CSS 문서) 불러와 연결
      (빈 태그)
      
        <img width="377" alt="html" src="https://user-images.githubusercontent.com/63788023/131248457-ff88c829-8902-408c-b570-b962d0b7df99.PNG">
        
      rel : (필수)현재 문서와 외부문서와의 관계를 지정
      href : 외부 문서의 위치를 지정
      
    + STYLE(CSS 작성하기)
      
      CSS를 HTML 문서 내부에 작성할 때 사용한다.
      
        <img width="334" alt="html2" src="https://user-images.githubusercontent.com/63788023/131248541-4a06b83a-a8c6-49a6-8b79-5f74fc70ea99.PNG">
        
    + SCRIPT(JS 불러오거나 작성하기)
     
      HTML 문서에서는 CSS를 link로 불러오거나 style안에 작성할 수 있다.
      JS는 `<script></script>`로 이 2가지 방식을 모두 사용할 수 있다.
      
        <img width="369" alt="html" src="https://user-images.githubusercontent.com/63788023/131248659-ba27fb51-5d0a-40fd-9667-b6257b56fa6b.PNG">
        
  + HTML 문서의 구조
   
     `<body></body>` 안에서 사용하는 태그들은 HTML 문서의 구조를 나타낸다.
     
     + DIV(막 쓰는 태그)
       단순히 특정 범위를 묶는(wrap) 용도로 사용한다. 보통 묶인 부분에 CSS나 JS적용
       
         <img width="360" alt="html" src="https://user-images.githubusercontent.com/63788023/131248778-c9930f6a-1b10-4608-ae4d-50d258f07de3.PNG">
         
     + IMG(이미지를 넣는 태그)
       
       `<img>`는 HTML에 이미지를 삽입할 때 사용한다.
       
         <img width="315" alt="html" src="https://user-images.githubusercontent.com/63788023/131248826-774d2751-8c9f-400d-9383-aa4d354c014a.PNG">
         
       src : (필수) 이미지의 URL
       alt : (필수) 이미지의 대체 텍스트를 지정
