# '??', '||', '&&'

## 서론 🤨

연산자를 잘 알고 적재적소에 사용한다면 훨씬 깔끔한 코드를 작성할 수 있을 것이다. 이왕 공부한 거 잘 정리해서 잘 써먹어보자✍️

## 본론 🧐

### Nullish 병합 연산자

> `??` 연산자는 피연산자들 중 첫 번째 정의가 되어있는 값을 찾을 수 있다.

여기서 정의되어 있는 값이란 `null`이나 `undefined`가 아닌 값을 말한다.

만약, 변수 `a`와 `b`를 가지고 정의되어 있는 값을 변수 `x`에다가 적용하고 싶다고 가정해보자. 아래와 같이 작성할 수 있을 것이다.

```javascript
let x;
if (a !== null && a !== undefined) {
  x = a;
} else {
  x = b;
}
```

고작 `x` 하나 정의하는 코드인데 너무,, 길다,,, 삼항연산자를 이용해보자!

```javascript
let x = a !== null && a !== undefined ? a : b;
```

위 식도 좋지만 여기서 `??`를 이용한다면 코드는 훨씬 간단해진다.

```javascript
let x = a ?? b;
```

만약 피연산자들의 수가 더 많아진다면 `??`는 더욱 진가를 발휘할 것이다 😎

하지만 언뜻보면 `??`와 `||`은 매우 유사해보인다.
`null`과 `undefined`는 `false`이니까, 그 외의 처음 만나는 값을 반환한다는 거에 대해서 같은 연산자가 아닌가???

### OR 연산자

> `||` 연산자는 피연산자들 중 첫 번째 `truthy`값을 찾을 수 있다.

자바스크립트는 `null`과 `undefined`를 제외하고도 `false`처럼 동작하는 많은 `falsy`값들이 존재한다.

아래와 같은 코드에 내 친구 `x`명을 할당해보자. 이 코드는 `x`가 거짓이 아니라면 기본적으로 `10`명을 할당해 줄 것이다.

```javascript
const 친구의수 = x || 10;
```

하지만 만약 내 친구가 0명이라면,,? 난 정말로 0명인데 자바스크립트는 이를 거짓으로 받아드릴 것이다,,`0`은 `falsy`한 값이기 때문에,,,

이 점이 `??`와 `||`의 차이이다. 위 코드를 아래와 같이 바꿔보자.

```javascript
const 친구의수 = x ?? 10;
```

위 코드는 내가 친구가 0명이라도 잘 할당해 줄 것이다. 이처럼 `??`와 `||`을 잘 구분해 사용하지 않으면 때때로 내 의도와 다르게 동작할 수 있다!

### AND 연산자

> `&&` 연산자는 피연산자들 중 첫 번째`falsy`값을 찾을 수 있다.

`falsy`값들을 제외한 모든 값을 `truthy`값이라고 한다. `&&` 연산자는 처음으로 만나는 `falsy`값을 반환한다.

```javascript
const something = 'SOMETHING' && false && NaN && 0 && ''; // false
```

`&&` 연산자와 `||`연산자는 피연산자들을 왼쪽부터 오른쪽으로 나아가며 판단하고, 원하는 값을 찾지 못할 경우 가장 마지막 값을 반환한다.

## 정리 🤓

- `??` : 처음 만나는 정의된 값을 반환
- `||` : 처음 만나는 참같은 값을 반환
- `&&` : 처음 만나는 거짓같은 값을 반환