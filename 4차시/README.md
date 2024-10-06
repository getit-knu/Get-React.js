# GET IT SW교육 React.js
## 4차시_state, 생명주기, hook
> 기간 : 24.10.06~24.10.09

### 🗂️4차시 자료🗂️
[React.js 4차시 자료](https://github.com/getit-knu/Get-React.js/blob/main/4%EC%B0%A8%EC%8B%9C/GETIT%20SW%20%EA%B5%90%EC%9C%A1%20react%20_%204%EC%B0%A8%EC%8B%9C.pdf)

👉자료를 다운 받은 후 수강해주세요!

### 🎞️4차시 강의🎞️
[![Video Label](http://img.youtube.com/vi/lxP8Xeq-12U/0.jpg)](https://youtu.be/lxP8Xeq-12U)

👉위 이미지를 누르면 강의를 들을 수 있습니다.

---

### 🚀목차🚀
1. state와 생명주기
2. hook

---

#### 01. 💫state와 생명주기
##### 📄state란?
: 리액트 컴포넌트의 변경가능한 데이터
- state가 변경될 때마다 재렌더링됨
  > 따라서 필요한 경우가 아니라면 state로 정의하지 말아야 함.
  > 쓸데없는 재렌더링으로 성능이 저하될 수 있기 때문.
- 쉽게 말해서, **변수**이다.
  > 단, 값이 변했을 때 관련 컴포넌트들이 재렌더링됨.
- 변경 가능한 데이터를 state를 통해 관리하는 것.
  
  
##### 🧐왜 state가 있어야 하나?
- `엘리먼트` : 리액트 앱을 구성하는 가장 작은 블록들
- `컴포넌트` : 입력받은 속성에 따라 그에 맞는 리액트 엘리먼트를 반환
> 컴포넌트는 붕어빵 틀, 엘리먼트는 붕어빵 자체라고 생각하면 됩니다.
---
#### ✨함수 컴포넌트, 클래스 컴포넌트
##### 함수 컴포넌트
: 함수 형태로 작성된 컴포넌트
```javascript
function Welcome(props){
  return <h1>Hello, {props.name}</h1>;
}
```

##### 클래스 컴포넌트
: (자바스크립트) 클래스 형태로 작성된 컴포넌트
```javascript
class Welcome extends React.Component{
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

---

#### 02. 💎props
##### props?
: 컴포넌트에 입력되는 속성들

- 컴포넌트는 입력받은 props에 따라 그에 맞는 리액트 엘리먼트를 반환한다.
> 붕어빵을 만들때 팥, 슈크림 등을 넣어서 다양하게 만들 수 있는 것처럼, 컴포넌트에 어떤 props가 들어가냐에 따라 다른 결과가 나옴.

---

#### 03. 🪂스타일링

##### 스타일링?
: 컴포넌트나 엘리먼트의 시각적 모양이나 레이아웃을 제어하는 과정
> 컴포넌트, 엘리먼트를 디자인하는 것이라고 생각하면 됩니다.

##### styled-components
- 컴포넌트 단위로 스타일링
- CSS 파일 없이 자바스크립트 내부에서 작성
- 동적 스타일링
- 재사용성, 유지보수

##### 📄설명서
##### 1. styled-components 설치 
: 터미널에 `npm install styled-components --save`

##### 2. styled-components 불러오기
```javascript
import styled from 'styled-components';
```

##### 3. 사용하기
```
const 컴포넌트이름 = styled.태그이름`
  css속성 : 속성값;
`;
```

---

### 📢과제
실습 결과 캡쳐 후 노션에 업로드하기(3차시 자료 참고)

👉 6기 노션 > SW과제제출 > React.js > 해당 차시 > 본인이름 > 과제제출란

👉 [6기 SW 과제제출 링크](https://www.notion.so/SW-8502eeef321b43e2ad13ece0f626be33)
