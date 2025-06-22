# TS에서의 Record

#typescript

Record는 TypeScript의 *유틸리티* 타입 중 하나로, 객체의 키-값 쌍의 타입을 정의할 때 사용

> ✅ *유틸리티*
> 유틸리티(Utility)는 프로그래밍에서 자주 사용되는 공통적인 기능들을 모아놓은 도구 모음

## 📍 Record<Keys, Type>
```javascript
// 1. 기본적인 Record 사용 예시
type UserRoles = Record<string, boolean>;

const userRoles: UserRoles = {
  admin: true,
  editor: false,
  viewer: true
}

// 2. 구체적인 키 타입을 지정한 예시
type Fruit = "apple" | "banana" | "orange";
type FruitPrice = Record<Fruit, number>;

const fruitPrices: FruitPrice = {
  apple: 1000,
  banana: 1500,
  orange: 2000
  // error: 다른 키는 추가할 수 없습니다!
}

// 3. 실무에서 자주 사용되는 예시
type CacheStore = Record<string, {
  value: any;
  timestamp: number;
}>

const cache: CacheStore = {
  "user-1": {
    value: { name: "선파" },
    timestamp: 1234567890
  }
}
```
## 📍 Record 사용의 장점 
1. 타입 안정성
	- 객체의 모든 키와 값에 대한 타입을 명확하게 정의 가능
	- 잘못된 타입의 값이 할당되는 것을 방지
2. 코드 가독성
	- 객체의 구조를 한눈에 파악 가능
3. 유지보수성
	- 타입 변경이 필요할 때 한 곳에서 수정 가능
