# script 선언 방식

## 서론 🤨

### head태그 내부에 script를 선언

> 1️⃣ `head`태그 내부에 속성 없이 선언  
> 2️⃣ `head`태그 내부에 `async` 속성과 함께 선언  
> 3️⃣ `head`태그 내부에 `defer` 속성과 함께 선언

### body태그 내부에 script를 선언

> 4️⃣ `body`태그 내부에 속성 없이 선언  
> 5️⃣ `body`태그 내부에 `async` 속성과 함께 선언  
> 6️⃣ `body`태그 내부에 `defer` 속성과 함께 선언

위 상황들의 차이점은 무엇일까?

## 본론 🧐

### ⚀ script태그를 만나면

브라우저는 `html`파일을 위에서 부터 읽다가 `scrip`태그를 만나면 `html`을 파싱하는걸 중지한다.  
그 후 `1. JS파일을 가져오는` 과정과 , `2. JS파일을 실행하는` 과정을 끝마친 후 나머지 `html`파일을 마저 파싱한다.

![without options](https://velog.velcdn.com/images/sunpaaaa/post/f24a4401-7811-4dde-a593-f8403145e8ec/image.png)

네트워크의 속도와 JS파일의 크기에 따라 사용자가 페이지를 이용할 수 있는 시간이 결정된다.

이러한 측면에서 `html`상단에 위치하는 `head`태그에 위치시키기보다, `body`태그의 제일 끝 부분에 위치시키는 것이 선호된다.

### ⚁ async 속성 사용

`async`은 불리언 값으로, 선언만으로 `true`의 값을 가진다.

![with async](https://velog.velcdn.com/images/sunpaaaa/post/af0e8811-2d20-47e1-8297-829323a8e908/image.png)

`async`와 함께 선언된 `script` 태그를 만나면,`html`을 파싱하면서 `1. JS파일을 가져오는` 과정을 병렬적으로 수행한다.  
이 과정이 끝나면, `html`파싱을 멈추고 `2. JS파일을 실행하는` 과정을 모두 수행한 후 멈췄던 `html` 파싱을 마저 수행한다.

이때 선언된 `scrip`가 여러 개라면, 선언된 순서에 상관없이 `1. JS파일을 가져오는` 과정을 끝마친 순서대로 `2. JS파일을 실행하는` 과정을 수행한다.

### ⚂ defer 속성 사용

`async`와 마찬가지로 불리언 값으로, 선언만으로 `true`의 값을 가진다.

![with defer](https://velog.velcdn.com/images/sunpaaaa/post/b32b69e6-a274-4012-8152-3b39588336ce/image.png)

`defer`와 함께 선언된 `script` 태그를 만나면,`html`을 파싱하면서 `1. JS파일을 가져오는` 과정을 병렬적으로 수행한다.  
`html`파싱이 모두 끝난 이후 `2. JS파일을 실행하는` 과정을 수행한다.

이때 선언된 `scrip`가 여러 개라면, 선언된 순서대로 `2. JS파일을 실행하는` 과정을 수행한다.

## 정리 🤓

사용자에게 화면을 보여주는 것이 먼저다.  
→ `body` 태그 마지막에 `script`를 추가하기  
→ 또는 `defer`와 함께 `head`에 추가하기
