
# **Spread Opertor**

스프레드 연산자는 ...를 통해 필요없는 쏙성을 빼거나 다른 속성을 추가할 수 있다. 빼는 것을 Rest, 추가하는 것을 spread라고 한다.

```jsx
class User {
    constructor(
        public name: string,
        public age: number,
        address: string,
        country: string){
            this.address = address;
            this.country = country;
    };
    address: string;
    country: string;
}

const user = new User('solchan', 24, 'YongIn', 'Korea');

const { country, address, ...nameAgeUser } = user;
console.log(user);
console.log(nameAgeUser);
/*
출력(user) -> User { name: 'solchan', age: 24, address: 'YongIn', country: 'Korea' }
출력(nameAgeUser) -> { name: 'solchan', age: 24 }
*/
```
<br>
16번 Line 코드를 보면 country, address를 user에서 빼고 이를 nameAgeUser로 만드는  동작을 한다. 출력 결과를 보면 namgAgeUserㄴ는 country, addresss가 빠진 상태로 출력됨을 알  수 있다.

user는 User라고 클래스 명을 출력해주지만 nameAgeUser는  country와 address 속성이 빠졌기 때문에 User클래스가 되지 못한다. 따라서 송성만 출력 되는 것을  알  수 있다.

```jsx
const part1: object = {
    name: 'solchan'
}

const part2: object = {
    country: 'Korea',
    address: 'YongIn',
}

const user = { ...part1, ...part2 };
console.log(part1);
console.log(part2);
console.log(user);
// 출력(part1) -> { name: 'solchan' }
// 출력(part2) -> { country: 'Korea', address: 'YongIn' }
// 출력(user) -> { name: 'solchan', country: 'Korea', address: 'YongIn' }
```

10번 Line 코드를 보면 part1, part2를 합하여 user를 만드는 것을 알 수 있다.
