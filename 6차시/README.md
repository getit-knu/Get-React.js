# GET IT SW교육 React.js
## 6차시_이벤트 핸들러
> 기간 : 24.11.06~24.11.10

### 🗂️6차시 자료🗂️
[React.js 6차시 자료](https://github.com/getit-knu/Get-React.js/blob/main/6%EC%B0%A8%EC%8B%9C/GETIT%20SW%20%EA%B5%90%EC%9C%A1%20react%20_%206%EC%B0%A8%EC%8B%9C.pdf)

👉자료를 다운 받은 후 수강해주세요!

### 🎞️6차시 강의🎞️
[![Video Label](http://img.youtube.com/vi/mcuyV2qkzNI/0.jpg)](https://youtu.be/mcuyV2qkzNI)

👉위 이미지를 누르면 강의를 들을 수 있습니다.

---

### 🚀목차🚀
1. 조건부 렌더링
2. 라우팅

---

#### 01. ⚡조건부 렌더링
#### 📢조건부 렌더링이란?
**: 말 그대로, 어떤 조건에 따라 렌더링이 달라지는 것**
- 쉽게 설명하면, 어떤 조건에 따라 화면에 보여지는 게 달라지는 것
  
  
#### App.js
```javascript
import { useState } from "react";
import LoginState from "./components/LoginState";
function App() {
  const [isLogin, setIsLogin] = useState(false);

  const handleLogin = () => {
    setIsLogin(!isLogin);
  };

  return (
    ‹div>
      ‹LoginState isLogin={isLogin} />
      <button onclick={handleLogin}>{isLogin ? "로그아웃" : "로그인"}</button>
    </div>
  );
}
export default App;
```

#### LoginState
```javascipt
function LoginState({ isLogin }) {
  return isLogin ? ‹WelcomeText /> : <LoginText />;
}
function LoginText() {
  return <h1>로그인 해주세요</h1>;
}
function WelcomeText () {
  return <h1>안녕하세요! 어서오세요~</h1>;
}
export default LoginState;
```
- App.js에 있는 버튼을 누르면 상태변수인 isLogin의 값이 반대로 바뀝니다.(true or false)
- 로그인 상태(isLogin)에 따라 버튼에 있는 텍스트가 바뀝니다.
- 로그인 상태에 따란 LoginState에서 보여주는 텍스트가 달라집니다.


![image](https://github.com/user-attachments/assets/eedb3e0a-b821-46c3-bda5-12e3035fc6ea)

- 버튼을 누를 때마다 isLogin의 값이 바뀌면서, 렌더링되는 텍스트나 컴포넌트가 달라집니다.

---

#### 인라인 조건문
- 조건문 자체를 코드에 넣는 것
- 어떤 조건문을 별도로 분리하지 않고, 조건문이 필요한 곳에 직접 넣어주 는 방식의 조건문을 말합니다.
- 논리 연산자( && AND)
  - '&&' 왼쪽에 있는 조건이 참이면, 오른쪽에 있는 것을 보여주는 방식
- 삼항 연산자(A? B:C)
  - ? 왼쪽에 있는 조건문이 참이면 -> : 왼쪽에 있는 것을 보여줌
  - ? 왼쪽에 있는 조건문이 거짓이면 -> : 오른쪽에 있는 것을 보여줌

![image](https://github.com/user-attachments/assets/fbde7d46-fcfb-45f9-a8a5-1b9c3ae5bf96)
- isLogin이 true, 즉 로그인이 되어 있는 상태일 때만 MyPageButton을 보여줌

---

#### 02. 🌟라우팅
#### 라우팅이란?
- 웹 애플리케이션에서 사용자의 요청에 따라 서로 다른 페이지나 뷰를 표시하는 것
- 브라우저에서 URL을 입력하거나 링크를 클릭하면 URL의 경로와 쿼리를 바탕으로 이에 해당하는 컴포넌트를 렌더링 해줌
- 리액트에서는 React-Router를 사용해서 라우팅을 구현

#### React-Router, 왜 쓰지?
- SPA에서 사용자 경험을 향상시키기 위한 것
- 뒤로가기 기능 : URL이 하나이면, 이전 페이지로 이동 불가
- 새로고침 기능 : 새로고침 하면 처음 페이지 대신 현재 페이지에서
- 페이지 특정 가능 : URL이 하나로 고정되면, 특정 페이지를 공유하거나 저장할 수 없음

#### react-router-dom 사용하기
1. 설치하기
- 터미널에 npm install react-router-dom --save

2. 불러오기
- import { BrowserRouter, Routes, Route } from 'react-router-dom'

3. 사용하기
- BrowserRouter
  - 라우팅에 대한 큰 틀. URL 기록들을 관리
- Routes
  - Route의 상위 상로에 있음. 현재 location에 맞는 Route를 찾아줌
- Route
  - URL과 컴포넌트를 매핑하여 라우팅을 처리함
  - 어떤 URL 경로가 입력되면, 해당 경로에 맞는 컴포넌트를 렌더링

---

1. BrowerRouter
- index.js에서 App을 Browser로 감싸기

2. Routes, Route
- 경로(path)와 그에 대해 렌더링할 컴포넌트(element)

3. useNavigate
- 버튼을눌렀을때 다른 페이지로 이동하게 하고 싶으면?
- useNavigate를 통해 다른 경로의 페이지로 이동가능

4. 버튼에 onClick 이벤트에 대한 이벤트 핸들러로 지정
![image](https://github.com/user-attachments/assets/d7bbe696-215f-432b-9a17-b37588c7b2f4)

---

### 📢과제
실습 결과 캡쳐 후 노션에 업로드하기(6차시 자료 참고)

👉 6기 노션 > SW과제제출 > React.js > 해당 차시 > 본인이름 > 과제제출란

👉 [6기 SW 과제제출 링크](https://www.notion.so/SW-8502eeef321b43e2ad13ece0f626be33)
