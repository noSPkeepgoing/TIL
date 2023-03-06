# CSS3 기본 문법

## CSS

- Cascading Style Sheets
- HTML이나 XML과 같은 구조화 된 문서를 어떻게 렌더링할 것인지 정의
- 즉 HTML의 각 요소의 스타일을 정의하여 어떻게 렌더링 할 것인지 브라우저에게 설명하기 위한 언어
- HTML은 CSS를 포함 가능하지만 CSS를 가지고 있지 않은 HTML은 브라우저에서 기본으로 적용하는 CSS(user agent stylesheet)에 의해 렌더링

## 선택자(Selector)

- 스타일을 적용하고자 하는 HTML 요소를 선택하기 위한 수단

![CSS Rule Set](./image/CSS%EB%A3%B0%EC%85%8B.png)

CSS Rule Set

- 셀럭터를 통해 선택된 모든 요소에 선언 블록에서 정의된 스타일을 적용
- 이와 같은 구문을 Rule Set이라하고 이들의 집합이 Style Sheet
- 복수개의 선택자 지정 가능
    - `h1, h2, p { color: blue }` 꼴로 쉼표(`,`)를 이용해 연속해 선택자 지정
- 선택자 패턴
    
    
    | 패턴 | Description |
    | --- | --- |
    | * | HTML 문서 내의 모든 요소를 선택. html 요소를 포함한 모든 요소가 선택 |
    | 태그명 | 지정된 태그명을 가지는 요소를 선택 |
    | #id 어트리뷰트 값 | id 어트리뷰트 값을 지정하여 일치하는 요소를 선택. id 속성 값은 중복 불가능 |
    | .class 어트리뷰트 값 | class 어트리뷰트 값을 지정하여 일치하는 요소를 선택. class 속성 값은 중복 가능 |
    | 셀렉터[어트리뷰트] | 지정된 어트리뷰트를 갖는 모든 요소를 선택 |
    | 셀렉터[어트리뷰트=”값”] | 지정된 어트리뷰트를 가지며 그 값이 어트리뷰트의 값과 일치하는 모든 요소를 선택 |
    | 셀렉터[어트리뷰트~=”값”] | 지정된 어트리뷰트의 값이 지정된 값을 공백으로 분리된 단어로 포함하는 요소를 선택 |
    | 셀렉터[어트리뷰트|=”값”] | 지정된 어트리뷰트의 값과 일치하거나 “값-”으로 시작하는 요소를 선택 |
    | 셀렉터[어트리뷰트^=”값”] | 지정된 어트리뷰트 값으로 시작하는 요소를 선택 |
    | 셀렉터[어트리뷰트$=”값”] | 지정된 어트리뷰트 값으로 끝나는 요소를 선택 |
    | 셀렉터[어트리뷰트*=”값”] | 지정된 어트리뷰트 값을 포함하는 요소를 선택 |
- 복합 선택자
    
    ![CSS복합선택자](./image/CSS%EB%B3%B5%ED%95%A9%EC%85%80%EB%A0%89%ED%84%B0.png)
    
    | 패턴 | Description |
    | --- | --- |
    | 셀렉터A 셀렉터B | 셀렉터A의 모든 후손(하위) 요소 중 셀렉터B와 일치하는 요소를 선택 |
    | 셀렉터A > 셀렉터B | 셀렉터A의 모든 자식 요소 중 셀렉터B와 일치하는 요소를 선택 |
    | 셀렉터A + 셀렉터B | 셀렉터A의 형제 요소 중 셀렉터A 바로 뒤에 위치하는 셀렉터B 요소를 선택 |
    | 셀렉터A ~ 셀렉터B | 셀렉터A의 형제 요소 중 셀렉터A 뒤에 위치하는 셀렉터B 요소를 모두 선택 |
- 가상 클래스 선택자
    - Pseudo-Class Selector
    - 요소의 특정 상태에 따라 스타일을 정의할 때 사용
    - CSS 표준에 의해 미리 정의된 이름을 사용

## 속성(Property)

```css
h1 {
	color: blue;
	font-size: 18px;
}
```

- 속성은 표준 스펙으로 이미 지정되어 있는 것을 사용, 사용자가 임의 지정이 불가능
- 여러개의 속성을 연속해서 지정 가능

## 속성 값(Value)

- 속성 값은 해당 속성에 사용 가능한 특정 단위로 지정
- 특정 단위로는 키워드, 크기 단위, 색상 표현 단위 등이 존재

## HTML과 CSS의 연동

- HTML에서 외부에 있는 CSS 파일을 로드
    
    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <link rel="stylesheet" href="css/style.css">
      </head>
      <body>
        <h1>Hello CSS!</h1>
        <p>just keep going</p>
      </body>
    </html>
    ```
    
    ```css
    h1 { color: white; }
    p  { background: black; }
    ```
    
- HTML 내부에 CSS를 포함
    
    ```html
    <!DOCTYPE html>
    <html>
      <head>
        <style>
          h1 { color: white; }
          p  { background: black; }
        </style>
      </head>
      <body>
        <h1>Hello CSS!</h1>
        <p>just keep going</p>
      </body>
    </html>
    ```
    
- HTML요소의 style 속성에 CSS를 기술
    
    ```html
    <!DOCTYPE html>
    <html>
      <body>
        <h1 style="color: white">Hello CSS!</h1>
        <p style="background: black">just keep going</p>
      </body>
    </html>
    ```