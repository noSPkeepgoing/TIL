# HTML 기본 문법

## HTML

- HyperText Markup Language
- 웹페이지의 내용(content)과 구조(structure)을 담당하는 언어

## 포함된 기능

- 멀티미디어(Multimedia)
  - 플러그인의 도움없이 비디오 및 오디오 기능을 자체적으로 지원
- 그래픽(Graphics & Effects)
  - SVG, 캔버스를 이용해 2차원 그래픽을 지원
  - CSS3, WebGL을 사용해 3차원 그래픽을 지원
- 통신(Connectivity)
  - 서버와의 소켓 통신을 지원함으로써 서버와의 양방향 통신이 가능
- 디바이스 접근(Divice acess)
  - 하드웨어 기능(카메라, 동작센서 등)을 직접적으로 제어
- 오프라인 및 저장소(Offline & Storage)
  - 오프라인 상태에서도 애플리케이션 동작 가능
  - 플랫폼으로 이용 가능
- 시맨틱 태그(Semantics)
  - 브라우저, 검색엔진, 개발자 모두에게 콘텐츠의 의미를 명확하게 설명 가능
- CSS3
  - CSS3 완벽 지원

## Hello World

- 대소문자 구분 없이 `<!DOCTYPE html>` 로 문서 형식을 HTML5으로 지정
- 실제적인 HTML document는 `<html>`과 `</html>` 사이에 기술
- `<head>`와 `</head>` 사이엔 브라우저에 표시되지 않는 HTML 문서에 대한 정보를 기술
- 웹브라우저에 출력되는 모든 요소는 `<body>`와 `</body>` 사이에 기술

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Hello World</title>
  </head>
  <body>
    <h1>Hello World</h1>
    <p>hello world!</p>
  </body>
</html>
```

## HTML의 요소와 어트리뷰트

### 요소(Element)

![HTML 요소](./image/HTML%EC%9A%94%EC%86%8C.png)

HTML 요소

- HTML 요소는 시작 태그와 종료 태그, 태그 사이에 위치한 콘텐츠로 구성
- HTML document는 요소들의 집합
- 태그는 대소문자를 구별하진 않으나 일반적으로 소문자를 사용
- 요소의 중첩이 가능
  - 요소는 다른 요소를 포함 가능
  - 이때 형성된 부자관계로 정보를 구조화
  ```html
  <!DOCTYPE html>
  <html lang="en">
    <head>
      <meta charset="UTF-8" />
    </head>
    <body>
      <h1>Hi there</h1>
      <p>good to see ya!</p>
    </body>
  </html>
  ```
- 빈 요소가 존재

  - content를 가질 수 없는 요소가 존재.
  - Empty element of Self-Closing element라 지칭
  - 오직 어트리뷰트만을 가짐

- 인라인 요소 vs 블럭 요소
  - 블럭 요소는 다른 요소(블럭, 인라인)를 포함 가능
  - 블럭 요소는 `margin` 값과 `padding` 값을 가질 수 있음
  - 인라인 요소는 블럭 요소는 포함 불가능
  - 인라인 요소는 다른 블럭 요소 안에 포함 되어 사용
  - 인라인 요소는 `witdh`와 `Height` 값을 가질 수 없음

### 어트리뷰트(Attribute)

![HTML 어트리뷰트](./image/HTML%EC%86%8D%EC%84%B1.png)

HTML 어트리뷰트

- 요소의 성질, 특징을 정의
- 요소의 추가적 정보를 제공
  ```html
  <!-- 이미지 파일의 경로, 파일명, 이미지의 너비, 이미지의 높이 정보를 브라우저에게 제공 -->
  <img src="HELLO.png" width="100" height="120" />
  ```
- 글로벌 어트리뷰트
  | Attribute | Description |
  | --------- | ---------------------------------------------------------------------------------- |
  | id | 유일한 식별자(id)를 요소에 지정. 중복 지정이 불가능 |
  | class | 스타일시트에 정의된 class를 요소에 지정. 중복 지정 가능 |
  | hidden | 브라우저에 노출되지 않게 함 |
  | lang | 지정된 요소의 언어를 지정. 검색엔진의 크롤링 시 웹페이지의 언어를 인식 가능하게 함 |
  | style | 요소에 인라인 스타일을 지정 |
  | tabindex | 사용자가 키보드로 이동할 때 순서를 지정 |
  | title | 요소에 관한 제목을 지정 |
