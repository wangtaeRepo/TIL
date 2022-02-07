# **Object && Type**
타입스크립트는 자바스크립트와 호환성을 위해 자바스크립트의 타입과 타입스크립트의 타입을 모두 지원한다.

## Type
| JavaScript | TypeScript |
| --- | --- |
| Number | number |
| Boolean | boolean |
| String | string |
| Object | object  |

## 변수
```jsx
// let: 코드에서 값이 변경도리 수 있음
let num = 123; // num: 123
num = 321; // num: 321
// const: 코드에서 값 변경이 불가능하며 선언시 초기화 필요
const name = 'solchan' // name: solchan
name = 'boy' // name: solchan, 불가능
```

<br>
타입스크립트에서 변수를 선언할 때, 타입을 지정할 수 있다.

```jsx
// JavaScript Code
let num: number = 123; // num: 123
num = 321; // num: 321
num = 'one'; // num: 123, string은 불가능

// TypeScript Code
const name: string = 'solchan' // name: solchan
const age: number = '24'; // X, number타입에 string 불가능
```

<br>
하지만 타입스크립트는 자바스크립트와 호환성을 위해 아래와 같이 선언하여도 타입 추론이 가능하다. 이를 타입 추론이라고 한다.

```jsx
let num = 123; // 123을 통해 number로 타입 추론
const name = 'solchan' // 'solchan'을 통해 string으로 타입 추론
```

<br>
혹은, any타입을 지정할 수 있다. any타입은  타입을 지정하지 않은 경우와 같이 동작한다.

```jsx
let val: any = 123; // 지금은 숫자
val = {}; // 지금은 객체
val = 'solchan'; // 지금은 문자열
```

마지막으로 undefined에 대해 알아보면, 최하위 타입으로 타입스크립트에서는 타입과 값으로 동작한다.

```jsx
let val: undefined = undefined; // 타입: undefined, 값: undefined
val = 1; // 불가능, val 타입이 undefined이기 때문에 number는 불가능
```
