
# **Class**

타입스크립트는 C++, JAVA와 같이 객체지향언어이다. 따라서 class, 접근 제한 키워드 private, proected, public 그리고 implements, extend와 같은 키워드를 제공한다.

그리고 constructor라는 생성자가 있는데, 객체 생성을 다음과 같이 할 수 있다.

```jsx
/* 아래 여러 방법으로 다음과 같은 객체를 생성할 수 있다. */
const user: User = new User('solchan', 24);
console.log(user);
// 출력 ->  User { name: 'solchan, age: 24}

/* 1번 */
class User {
    constructor(name: string, age: number) {
        this.name = name;
        this.age = age;
    }
    name: string;
    age: number;
}
/* 2번 */
/* 생성자 파라미터 부분에 아래처럼 하여 속성 정의를 생략할 수 있다. */
class User {
    constructor(public name: string, public age: number) {}
}
```
<br>
인터페이스 구현

```jsx
// 이름과 나이를 정의하는 인터페이스를 상속하는 클래스
interface User {
    name: string;
    age?: number;
}

class UserClass {
    constructor(public name: string, public age: number){]}
}
const user: UserClass = new UserClass('solchan', 24);
console.log(user);
// 출력 -> UserClass { name: 'solchan', age: 24 }
```

interface의 age는 필수가 아닌 선택으로 정의됐지만, 클래스가 인터페이스를 구현하는 경우에는 반드시 속성으로 포함되어야 한다.

타입스크립트는 다른 객체지향 언어처럼 abstract 키워드를 통해 아래와 같이 추상 클래스를 만들어 사용할 수 있다. 

```jsx
abstract class AbstractUser {
    abstract name: string;
    constructor(public age: number) {};
}
class user extends AbstractUser{
    constructor(public name: string, age: number){
        super(age); // super()는 부모 클래스의 생성자를 호출한다. 
    };
/* 부모 클래스의 name이 abstract이기 때문에, 구현 구문을 작성한다.
생성자 구문에 작성하였다. */
}

console.log(new user('solchan', 24));
// 출력 -> user { age: 24, name: 'solchan' }
```
