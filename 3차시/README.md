# GET IT SW교육 React.js
## 3차시_컴포넌트,props
> 기간 : 24.10.02~24.10.05

### 🗂️3차시 자료🗂️
[React.js 3차시 자료](https://github.com/getit-knu/Get-React.js/blob/main/3%EC%B0%A8%EC%8B%9C/GETIT%20SW%20%EA%B5%90%EC%9C%A1%20react%20_%203%EC%B0%A8%EC%8B%9C.pdf)

👉자료를 다운 받은 후 수강해주세요!

### 🎞️3차시 강의🎞️
[![Video Label](http://img.youtube.com/vi/YTooyIVNPYc/0.jpg)](https://youtu.be/YTooyIVNPYc)

👉위 이미지를 누르면 강의를 들을 수 있습니다.

---

### 🚀목차🚀
1. 컴포넌트란?
2. props란?
3. 스타일링

---

#### 01. 🍃컴포넌트란?
: 어떠한 속성을 받아서 그에 맞는 출력을 리턴해주는 것<br/>
> 붕어빵 틀이라고 생각하면 됩니다. 붕어빵 틀이 있으면 붕어빵을 찍어낼 수 있죠? 붕어빵 틀이 붕어빵을 찍어낸다면, 컴포넌트는 리액트 찍어내는 틀입니다.

#### 📌중요한 점
##### 1. 리액트는 컴포넌트 기반 구조
- 리액트에서 컴포넌트는 **UI를 구성하는 기본 단위**입니다.
- 모든 페이지가 **컴포넌트**로 구성되어있고, 컴포넌트는 **다른 컴포넌트의 조합**으로 구성될 수 있습니다.
- **재사용가능**한 코드 블록
  
##### 2. 컴포넌트와 엘리먼트의 차이점
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
