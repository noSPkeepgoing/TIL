# HTML5?

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
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello World</title>
</head>
<body>
    <h1>Hello World</h1>
    <p>hello world!</p>
</body>
</html>
```