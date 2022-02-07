
# **인터페이스**
타입스크립트에서 object 타이비으로 선언된 변수는 number, boolean, string 타입의 값을 가질 수는 없지만, 속성이 다른 objeect에 대해서는 마치 any 타입처럼 담겨진다.

```jsx
let obj: object = { name: 'solchan'};
obj = { name: 'sochan', age: 24};
```
<br>
1번 코드에는 name만을 갖는 objectdlrh, 2번 코드는 name, age를 갖는 object입니다. 서로 송성이 다르지만, object로 타입이 같아 위 코드가 가능하아. 이런 부분을 해결하기 위해 인터페이스 구문이 고안되었고, 아래와 같은 방법으로 사용된다. 

```jsx
// 위 인터페이스를 통해 예시를 보면
interface User {
    name: string;
    age: number;
    phone?: string; // 변수명 + ? 는 선택 항목을 뜻한다.
}

let user1: User = { name: 'solchan', age: 24 }
// user1 -> 필수 항목인 name과 age 모두 초기화, 성공!
let user2: User = { name: 'solchan', phone: '123-123' }
// user2 -> 팔수 항목인 age가 없엄, 오류!
let user3: User = { name: 'solchan', age: 24, location: 'YongIn' }
// user3 -> 필수 항목이 모두 있지만 location은 인터페이스에 없음, 오류!
let user4: User = { name: 'sochan', age: 24, phone: '123-123' }
// user4 -> 필수가 모두 존재하고 phone은 선택으로 존재한다, 성공!
```
<br>
익명의 인터페이스는 주로 함수에서 사용된다.

```jsx
let account: { email: string, password: string } = { 
	email: 'solchan@interface.hello', password: 'typescript' 
}

function printMe( me: { name: string, age: number }) {
    console.log( `name: ${me.name}, age: ${me.age}` )
}

printMe({ name: 'solchan', age: 24});
```
