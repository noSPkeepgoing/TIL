##  📍 패키지 매니저 vs 빌드 툴

### 📦 패키지 매니저 (예: yarn, npm, pnpm)
- 라이브러리 설치 도구! (`react`, `axios` 같은 걸 설치함)
- `node_modules` 폴더와 `package.json` 관리
- `yarn start`, `yarn build` 같은 명령 실행도 해줌 (근데 실제로는 내부 명령어를 실행하는 거임)
- ❌ 직접 코드 변환이나 빌드는 하지 않음!

### 🛠️  빌드 툴 (예: Vite, webpack, Parcel)
- 코드를 진짜로 "번들링"하거나 "트랜스파일" 해줌
- 여러 파일을 하나로 묶고, 최적화해주는 애들
- 브라우저가 이해할 수 있게 ES6+ 코드를 바꿔줌
- 혼자 쓸 수 없고, 설치된 패키지가 필요해서 패키지 매니저랑 같이 써야 함

---
## 📍 Vite는 빌드 툴, yarn은 패키지 매니저

- Vite는 빠른 개발 서버 + 빌드 도구
- yarn은 그냥 명령어 실행할 뿐이지, 빌드는 하지 않음
- 예: `yarn build`를 치면 실제로는 `vite build`를 실행하는 구조임

---
## 📍 왜 헷갈렸을까? → CRA 때문!

- CRA(Create React App)는 초보자용 올인원 도구
- `yarn build`만 쳐도 빌드가 되니까 yarn이 빌드까지 해주는 줄 알게 됨
- 사실은 내부에서 `react-scripts`가 `webpack`을 실행하는 거였음

---

## 📍 CRA vs Vite 비교 🔍

|항목|CRA|Vite|
|---|---|---|
|빌드 도구|webpack|rollup 기반 (내장)|
|개발 서버|react-scripts|vite|
|설정|거의 없음|자유도 높음 (`vite.config.ts`)|
|속도|느린 편|빠름⚡|
|유연성|낮음|높음|
|처음 배우기|쉬움 👶|중급 이상 👨‍💻|

---

## 📍 패키지 매니저 + 빌드툴 통합 도구들 

### ✅ Deno
- 설치, 실행, 빌드까지 전부 포함된 JS/TS 런타임
- `deno run`, `deno bundle`, `deno test` 다 지원함

### ✅ Bun
- 아주 빠른 JS 런타임 + 패키지 매니저 + 빌드 도구
- `bun install`, `bun build`, `bun test` 등 한번에 다 가능

---
## 🧠 한눈에 정리

|도구|패키지 설치|빌드|비고|
|---|---|---|---|
|yarn/npm/pnpm|✅|❌|설치만 가능|
|Vite|❌|✅|빌드만 가능 (설치 필요함)|
|CRA (react-scripts)|❌|✅|내부에 webpack 있음|
|Deno|✅|✅|올인원 도구!|
|Bun|✅|✅|빠르고 통합된 도구|
|Parcel|❌|✅|자동화 빌드 도구|

---

## 🔚 요약 한 줄로!

> yarn은 설치만, Vite는 빌드만!  
> CRA는 둘 다 되는 것처럼 보이지만 내부에 webpack이 숨어 있음 👀
