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