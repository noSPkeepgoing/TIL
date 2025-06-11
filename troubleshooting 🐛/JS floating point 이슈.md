# 부동소수점 이슈
#Javascript

### 🤔 문제 상황
```js
0.7 * 90 // 기대값: 63
```
- 실제 결과: `62.99999999999999`
- 계산은 맞지만, **소수점 오차**가 발생함
  
### 🧐 원인
JS는 `IEEE 754` 방식의 부동소수점(64bit)으로 숫자를 처리함  
→ 일부 소수는 *정확히 표현 불가* (이진법 한계)

예:
```js
0.1 + 0.2 // 0.30000000000000004
```

### ✅ 해결 방법
#### 1. `toFixed()` + `Number()`
```js
Number((0.7 * 90).toFixed(2)) // 63
```

- 소수점 자리수 조절 (`toFixed`)
- 문자열 → 숫자로 변환 (`Number`)

> 💡 깔끔한 숫자 결과 필요할 때 유용

#### 2. `toLocaleString()` (표시용)
```js
(0.7 * 90).toLocaleString(undefined, { maximumFractionDigits: 2 }) // "63"
```
- 숫자 → 보기 좋게 문자열로 포맷
- 소수점 자리수 조절 가능

> 💡 **UI 표시 전용** (계산에는 불적합)

### 🧪 테스트
```js
const raw = 0.7 * 90;
console.log(raw); // 62.99999999999999

console.log(Number(raw.toFixed(2))); // 63
console.log(raw.toLocaleString(undefined, { maximumFractionDigits: 2 })); // "63"
```
 
### 📝 정리
- 계산 정확도 필요하면 .toFixed() 사용
- UI 출력은 `.toLocaleString()`도 OK
- 더 정밀한 계산은 `BigNumber.js` 같은 라이브러리 고려

### 🔗 참고
- [MDN - toFixed()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toFixed)
- [MDN - toLocaleString()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Number/toLocaleString)
- [JS 부동소수점 문제 설명 사이트](https://0.30000000000000004.com/)
