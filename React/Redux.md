# **Redux**

리덕스는 리액트에서 가장 많이 사용되는 상태 관리 라이브러리중 하나이다. 리덕스를 사용하면 컴포넌트의 상태 업데이트 관련 로직을 다른 파일로 분리시켜서 효율적으로 관리할 수 있다.

### Redux의 기본 개념 : 세가지 원칙

1. Single Source of Truth
    
    하나의 애플리케이션 안에는 하나의 스토어만 사용하자는 원칙이다. 이렇게 하면 애플리케이션의 디버깅이 쉬워지고 서버와의 직렬화가 될 수 있고 쉽게 클라이언트에서 데이터를 받아들여올 수 있게 된다.
    
2. State is read-only
    
    상태를 변화시키는 방법은 오직 액션을 일으키는 것이다. 이것은 상태를 변화시키는 의도를 정확하게 표현할 수 있고, 상태 변경에 대한 추적이 용이해지게 된다.
    
3. Changes are made with pure functions
    
    변화를 일으키는 리듀서 함수는 순수한 함수여야 한다. 순수 함수는 다음과 같은 조건을 만족한다.
    
    - 리듀서 함수는 이전 상태와 액션 객체를 파라미터로 받는다.
    - 파라미터 외의 값에는 의존하면 안된다.
    - 이전 상태는 절대로 건드리지 않고, 변화를 준 새로운 상태 객체를 만들어서 반환한다.
    - 똑같은 파라미터로 호출된 리듀서 함수는 언제나 똑같은 결과 값을 반환해야 한다.

### Store

상태가 관리되는 오직 하나의 공간

- 컴포넌트와는 별개로 스토어라는 공간이 있어서 그 스토어 안에 앱에서 필요한 상태를 담는다.
- 컴포넌트에서 상태 정보가 필요할 때 스토어에 접근한다.

### Action

상태에 변화가 필요하다면 액션을 일으켜야한다. 액션은 객체로 표현되며 type필드를 반드시 가지고 있어야 한다.

### Dispatch

스토어의 내장 함수 중 하나인 디스패치는 액션 객체를 넘겨줘서 상태를 업데이트 하는 유일한 방법이다. 이벤트 트리거라고 생각할 수 있다.

### Subscribe

스토어의 내장 함수 중 하나인 구독은 리스너 함수를 파라미터로 넣어 호출하면 상태가 업데이트될 때마다 호출된다. 일종의 이벤트 리스너라고 볼 수 있다.

### Reducer

- Action을 Store가 바로 전달하는 것이 아니라 Reducer를 통해 전달한다.
- Reducer(리듀서)가 주문을 보고 Store(스토어)의 상태를 업데이트하는 것이다.
- Action(액션)을 Reducer(리듀서)에 전달하기 위해서는 dispatch() 메소드를 사용해야한다.

### **Redux 구조**
<img src="https://raw.githubusercontent.com/wangtaeRepo/TIL/main/img/React/redux-structures.png" width="600px">

<br>

### **리덕스 상태 변화의 흐름**
<img src="https://raw.githubusercontent.com/wangtaeRepo/TIL/main/img/React/redux-data-flow.gif" width="600px">

### Redux의 장점

- 상태를 예측 가능하게 만든다. (순수함수를 사용하기 때문)
- 유지보수 (복잡한 상태 관리와 비교)
- 디버깅에 유리 (action과 state log 기록 시) → redux dev tool (크롬 확장)
- 테스트를 붙이기 용의 (순수함수를 사용하기 때문)

### **Redux에서 위 개념을 구현하는 두 가지 방법**

+ mapStateToProps()
+ Redux hooks (비교적 최근에 나온 기술)
> + useSelector
> + useDispatch

---

### Ref.

[](https://hanamon.kr/redux%EB%9E%80-%EB%A6%AC%EB%8D%95%EC%8A%A4-%EC%83%81%ED%83%9C-%EA%B4%80%EB%A6%AC-%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC/)

[Redux - 1. 수업소개](https://www.youtube.com/watch?v=Jr9i3Lgb5Qc&list=PLuHgQVnccGMB-iGMgONoRPArZfjRuRNVc&index=1)