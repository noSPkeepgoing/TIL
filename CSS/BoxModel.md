# 박스 모델

- 모든 HTML 요소는 Box 형태의 영역이 존재
  ![박스모델](./image/CSS%EB%B0%95%EC%8A%A4%EB%AA%A8%EB%8D%B8.png)
  박스모델
- Box는 Content, Padding, Border, Margin으로 구성
  | 명칭 | 설명 |
  | ------- | ------------------------------------------------------ |
  | Content | 요소의 실제 내용이 위치하는 영역 |
  | Padding | 테두리(Border) 안쪽에 위치하는 요소의 내부 여백 영역 |
  | Border | 테두리 영역 |
  | Margin | 테두리(Border) 바깥쪽에 위치하는 요소의 외부 여백 영역 |

## width / height 프로퍼티

- 요소와 너비를 지정하기 위해 사용
- **콘텐츠 영역**을 대상으로 적용

## margin / padding 프로퍼티

- 콘텐츠의 4개 방향(top, bottom, right, left)으로 지정 가능

![Untitled](./image/CSS%EC%BD%98%ED%85%90%EC%B8%A0%EB%B0%A9%ED%96%A5.png)

- margin 프로퍼티를 `auto`로 지정하면 브라우저 중앙에 위치
- margin은 음수 값을 가질 수 있지만 padding은 불가능
