# GET IT SW교육 React.js
## 5차시_이벤트 핸들러
> 기간 : 24.11.01~24.11.05

### 🗂️5차시 자료🗂️
[React.js 5차시 자료](https://github.com/getit-knu/Get-React.js/blob/main/5%EC%B0%A8%EC%8B%9C/GETIT%20SW%20%EA%B5%90%EC%9C%A1%20react%20_%205%EC%B0%A8%EC%8B%9C.pdf)

👉자료를 다운 받은 후 수강해주세요!

### 🎞️5차시 강의🎞️
[![Video Label](http://img.youtube.com/vi/mWd71gf4UlE/0.jpg)](https://youtu.be/mWd71gf4UlE)

👉위 이미지를 누르면 강의를 들을 수 있습니다.

---

### 🚀목차🚀
1. 이벤트 핸들러
2. argument 전달
3. to-do-list 만들기

---

#### 01. 💫이벤트 핸들러
#### 📢이벤트란?
**: 말 그대로, '사건'을 말함**
- 사용자가 버튼을 클릭하는 것도 하나의 사건
- 이러한 이벤트가 발생했을 때, 어떤 동작을 하도록 만들 수 있어야 함
- 그래야 버튼을 눌렀을 때, 다른 페이지로 이동하거나 좋아요 가 늘어가거나 다른 사람을 팔로우할 수 있음
- 다양한 이벤트를 알고 이것들을 활용할 수 있어야 함

  
#### 🧐이벤트 핸들러
**: 이벤트가 발생했을 때 실행되는 함수**
> 예를 들어 버튼에 클릭 이벤트가 발생했을 때 어떤 함수가 실행되도록 만들려면, 그 버튼의 onClick={} 안에 그 함수를 넣으면 됩니다.

```react.js
function AlertComponent(){
  const handleClick = () => {
    alert("Button clicked!");
  };
  return <button onClick={hancleClick}>Click me!</button>;
}

function App() {
  return <AlertComponet />;
}

export default App;
```
- onClick 이벤트가 발생했을 때, handleClick 함수가 발생
- 이 handleClick 함수가 바로 이벤트 핸들러
- onClick 이벤트가 발생했을 때 handleClick 함수가 실행되고, handleClick 함수를 보면 알림창이 출력된다는 것을 알 수 있음
  - 즉, 버튼을 누르면 알림창이 뜸
    
![image](https://github.com/user-attachments/assets/9b534480-4e6b-482b-bf3a-ac2cfd5ab670)
- 'Click me!' 버튼을 누르면 알림창이 뜨는 걸 볼 수 있습니다.

---

#### 💁일반 함수 vs 화살표 함수
이벤트 핸들러는 대표적으로 두 가지 방법으로 표현함
- **일반 함수** : function 키워드 사용
```react.js
function regularFumction(x, y) {
  return x+y;
}
```
- **화살표 함수** : () => 형식으로 작성 / '=>' 화살표 기호 사용
```react.js
const arrowFucntion = (x,y) => x+y;
```

#### 🔆react vs html
- html 에서는 click 이벤트를 `onclick`으로 표기
- react 에서는 click 이벤트를 `onClick`으로 표기
  - 이러한 표기를 **카멜 표기법** 이라고 함
  - 첫 글자를 소문자, 그 다음 단어부터는 첫 글자를 대문자로 표기하는 것
  - ex)camelCase, isCamelCase


#### 🗨️이벤트의 종류
- `onClick` : 클릭 이벤트. 버튼이나 다른 요소기ㅏ 클릭될 때 발생합니다.
- `onDoubleClick` : 더블클릭 이벤트, 요소가 두 번 연속으로 클릭될 때 발생합니다.
- `onKeyDown` : 키보드를 눌렀을 때 발생합니다.
- `onKeyUp` : 키보드를 맬 때 발생합니다.
- `onChange` : 폼 요소의 값이 변경될 때 발생합니다.

- 이벤트는 종류가 많습니다. 때문에 어떤 이벤트에 대한 처리를 하고 싶다면, 그 이벤트를 검색하면서 직접 찾아보면 좋습니다.
  
---

#### 02. 🌟argument 전달
#### 이벤트 핸들러에 argument 전달하기
- **이벤트 핸들러** : 어떤 이벤트가 발생했을 때 실행되는 함수
- 이 함수에 argument를 전달해야 하는 경우가 발생하기도 합니다.
```react.js
function AlertComponent(){
  const handleClick = (e) => {
    alert(e.target.innerText);
  };
  return (
    <div>
      <button onClick={handleClick}>Click me!</button>
    </div>
  );
}

function App() {
  return <AlertComponet />;
}

export default App;
```

> - onClick 이벤트가 발생하면, handleClick 함수 실행
>>  - 이때 handleClick 함수는 e라는 argument를 받음.
>>  - 이 e는 '발생한 이벤트'에 대한 정보를 담은 객체
>>  - e : 이벤트 객체
> - e.target은 이 이벤트 요소를 가리킴
> - e.target.innerText는 이벤트 요소 안에 있는 텍스트를 말함
>>  - 즉, 클릭된 버튼의 텍스트
>- 따라서 이 코드는 클릭 이벤트가 발생했을 때 그 클릭된 버튼의 텍스트를 알림창에 띄우는 코드



#### 비동기(Asynchronous)
- 여러 작업이 동시에 진행되는 것.(순서 보장X)
- 코드의 흐름이 복잡하고 이해하기 어려움
- 블로킹이 발생하지 않음.
- 성능 저하를 방지할 수 있음.

---

#### 🍃생명주기
- 사람이 태어나고 살다가 죽는 것처럼, 컴포넌트도 생성되고 사라짐.
- 이러한 **컴포넌트의 생성~소멸**을 '생명주기'라고 함.
- 컴포넌트는 계속 있는 게 아니라, 생성되고 업데이트되다가 사라짐.

---

#### 02. 🍦hook
> 이전에는 함수 컴포넌트에서 state를 정의하여 사용하거나 컴포넌트의 생명주기에 맞춰 어떤 코드를 실행할 수 없었음.
> 클래스 컴포넌트에서만 가능했었음. <br/>
> 하지만 `hook`이 생기면서 **함수 컴포넌트에서도 클래스 컴포넌트에서만 쓰던 기능들을 쓸 수 있게 됨.**

#### 📄hook?
**: 리액트 컴포넌트에서 상태(state)와 생명주기(lifecycle) 기능 등을 사용할 수 있께 해주는 함수**
- 모두 `use`라는 단어로 시작함.
  > ex) useState, useEffect, useRef 등
- hook의 도입으로 함수 컴포넌트에서도 이러한 기능을 활용할 수 있게 된 것.


#### ⚓대표적인 hook
- `useState` : 컴포넌트에서 상태를 관리하기 위한
- `useEffect` : 컴포넌트의 생명주기 중 특정 시점에 코드를 실행하기 위한

---

#### 📌useState
**: state를 관리하기 위한 훅**
- 예시
```react.js
const [변수명, set변수명] = useState(초깃값);
```
- useState()안에 값을 넣어서 state의 초깃값을 설정
- 상태 변수를 바꾸려면 해당 state의 set 함수에 값을 넣어서 변경

---
#### 📌useEffect
**: 사이드 이펙트를 수행하기 위한 훅**
- 컴포넌트에서 제공하는 생명주기 함수인 `componentDidMount()`,`componentDidUpdate()`,`componentWillUnmount()`의 기능을 하나로 통합해서 제공
- 예시
```react.js
useEffect(이펙트 함수, 의존성 배열);
```
- 배열에 있는 변수 중에 하나라도 변경되면 이펙트 함수 실행

#### 1. 의존성 배열이 빈 배열([])인 경우
: 마운트, 언마운트 시에만 이펙트 함수 실행
```react.js
import React, { useEffect, useState } from 'react';

function MyComponent() {
  useEffect(() => {
    console.log('컴포넌트가 마운트되었습니다.');

    return () => {
      console.log('컴포넌트가 언마운트되었습니다.');
    };
  }, []); // 마운트 시 한 번 실행, 언마운트 시 클린업 실행

  return <div>My Component</div>;
}
```

#### 2. 의존성 배열을 생략한 경우
: 렌더링 할때마다 이펙트 함수 실행
```react.js
const [count, setCount] = useState(0);

useEffect(() => {
  console.log('매 렌더링 때 실행');
}); // 의존 성 배열을 생략하면 모든 렌더링마다 실행
```

#### 3. 의존성 배열에 변수가 있는 경우
: 변수들 중 하나가 바뀌면 이펙트 함수 실행
```react.js
const [count, setCount] = useState(0);

useEffect(() => {
  console.log('value가 ${value}로 변경되었습니다.');
}, [value]);// value가 변경될 때마다 실행
```

---

#### ✨hook의 규칙
#### 1. 최상위 레벨에서 호출하기
- 조건문이나 반복문 안에 직접 넣으면 안 됨.
- 중첩된 함수 안에서도 X.

#### 2. 리액트 컴포넌트에서 호출
- 일반적인 자바스크립트 함수에서 호출 X.
- 함수 컴포넌트나 컴스텀 훅에서만 사용 가능
  
---

### 📢과제
실습 결과 캡쳐 후 노션에 업로드하기(4차시 자료 참고)

👉 6기 노션 > SW과제제출 > React.js > 해당 차시 > 본인이름 > 과제제출란

👉 [6기 SW 과제제출 링크](https://www.notion.so/SW-8502eeef321b43e2ad13ece0f626be33)
