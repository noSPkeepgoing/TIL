# 왜 타입방어가 되지 않을까?

#TypeScript #Tanstack-Table

## 📍 간단 상황 설명

> `tanstack table`을 이용해서 테이블 값을 세팅하는 상황
> `formatYYYYMMDDWithSeparator` 함수는 첫 번째 인자로 `string` 을 취하고, `renderValue()` 반환값의 type은 `string | null`

## 📍 생각 오류

아래와 같이 작성하면 타입방어가 가능하여 정상 작동 할 것이라 생각함
(👩🏻‍💻 : renderValue의 반환값이 falsy라면 ''반환, truthy라면 string으로 변환해줘야지! )
``` javascript
	columnHelper.accessor('expirationDate', {
	header: '소비기한',
	cell: ({ renderValue }) =>
	renderValue()
	? formatYYYYMMDDWithSeparator(renderValue().toString(), '.')
	: '',
	}),
```
 *Argument of type 'string | null' is not assignable to parameter of type 'string'.  Type 'null' is not assignable to type 'string'.* error 발생
 
## 📍 문제 상황

1. `renderValue()`를 두 번 호출하고 있음 !
2. 두 번째 호출의 결과는 첫 번째 체크와 다를 수 있음 !!

## 📍 해결 방법

1. 변수를 이용해 `renderValue()`값을 한 번만 호출
2. 값의 존재 여부를 명확하게 체크 -> 타입방어!
``` javascript
columnHelper.accessor('expirationDate', {
header: '소비기한',
cell: ({ renderValue }) => {
const value = renderValue();
return value ? formatYYYYMMDDWithSeparator(value.toString(), '.') : '';
},
})
```

당연한건데, 너무 얕은 사고를 하다보니 놓쳐버린 거 같다.🤦‍♀️
