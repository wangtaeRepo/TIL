
# **Destructuring Assignment**

구조 분해 할당은 객체와 배열 모두 사용 가능하다. 여기서 객체에 대한 구조 분해 할당을 알아보자

```jsx
class User {
    constructor(
        public name: string, 
        public age: number, 
        public location: string){};
}
const user1 = new User('solchan', 24, 'Y');

const { age, name: nickname, location: loc } = user1;
console.log(`이름: ${nickname}, 나이: ${age}, 지역: ${loc}`)
// 출력 -> 이름: solchan 나이: 24 지역: Y
```

User1 객체에서 name을 nickname이라는 이름으로, location을 loc로, age는 그대로 꺼내어 마치 단독 변수 처럼 사용할 수 있다.
