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
1. 이벤트 핸들러
2. argument 전달
3. to-do-list 만들기

---
#### ⚠️5차시 참고사항
> 5차시에서 'argument 전달' 부분에는 이벤트 객체에 대한 부분만 담았습니다. 이벤트 객체 외에 다른 argument를 직접 전달하는 방법은 'to-do-list 만들기' 부분에서 삭제 기능을 만드는 부분을 참고해주세요~ 

> 38분 50초부터 코드 및 파일 구조를 설명하는 부분이 있습니다.
> 앞부분 설명으로 to-do-list를 만들기 어려우시면, 38분 50초부터 있는 설명을 참고해주세요. 만약 pdf를 사용한 설명만으로도 이해가 되신다면, 파일 구조 설명만 보고 넘기셔도 됩니다.

> 파일 구조 설명은 40:20~46:36 입니다.
> 그 뒷부분은 pdf 자료를 활용한 설명(앞부분 설명)과 중복됩니다.

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


![image](https://github.com/user-attachments/assets/46370694-2b02-4191-b3f1-c1e3cd63df58)
- 'Click me!' 버튼을 눌렀기 때문에 알림창에 'Click me!'가 출력되는 걸 볼 수 있습니다.
- 만약 버튼에 다른 텍스트가 있으면 그 텍스트가 알림창에 출력되겠죠?


#### 🚀 input 태그 내용 관리하기
- input 태그에 텍스트를 입력할 수 있지만, 입력된 텍스트를 관리 하려면 입력되는 텍스트를 저장해야 합니다.
- 이를 위해서는, input 태그에 입력된 내용이 바뀔 때마다 그 내 용을 저장해야 함
- 요소 값이 변경될 때 발생하는 이벤트인 onChange를 사용해서 그때마다 해당 요소 값을 특정 변수에 저장해야 함
- 실시간으로 변수에 반영되어야 하므로 상태 변수를 사용해야 함

> - input 태그에 onChange 이벤트가 발생할 때마다 handleChange 실행
> - handleChange는 이벤트 요소의 값 (e.target.value)을 inputText라는 상태 변수 저장
> - 그리고 input 태그의 값(value 속성) 을 inputText로 결정해줌
> - 그리고 'submit' 버튼을 눌렀을 때 inputText의 값이 알림창에 나타남.

---

#### 03. 🍦to-do-list 만들기
#### 1. 입력 받은 내용을 list에 추가하기
- input 태그에 텍스트를 입력하고 '추가' 버튼을 누르면, 입력된 텍스트가 list에 추가되게 하기
- input 태그에 입력되고 있는 텍스트를 저장할 상 태변수와, 입력되어 제출된 텍스트들을 저장할
list에 대한 상태 변수가 필요함

---

- 앞에서 설명했던 input 태그를 관리하는 코드를 사용합니다. (앞에서 설명했으니 생략하겠습니다.)
- useState로 list를 저장할 상태변수를 만듭니다.
> 이때 초깃값은 빈 배열(D)로 설정해줍니다.

- 그리고 '추가' 버튼을 누르면, 다음 두 가지를 실행 하도록 합니다.
  - input Text의 내용을 list에 추가해서 업데이트
해주기
  - inputText의 내용을 으로 만들어서 input 태
그 안에 내용을 비워주기
- 화면을 통해 list의 내용물을 볼 수 있음

![image](https://github.com/user-attachments/assets/263a9cd5-89ca-49d9-b59e-d85dab5bcba3)
- 실행해보면 '추가' 버튼을 누를 때마다 list에 해당 내용이 추가되는 것을 확인할 수 있습니다.
  
---

#### 2. list의 요소들을 한 줄씩 출력하기
- list 자체를 보여주는 게 아니라, list에 담긴 내용들을 한 줄씩 출력해 서 목록 형태로 보여줘야 합니다.
- 즉, 반복문을 이용해 list의 요소들을 하나씩 태그로 감싸서 화면에 보 여줘야 합니다.
- 일반적인 반복문을 사용할 수도 있지만, js에 있는 map이라는 메서 드를 이용해서 list에 있는 요소에 접근해보겠습니다.
  - map은 배열의 각 요소에 특정 작업을 수행한 결과(새로운 배열)
를 반환하는 메서드입니다.
- u 태그와 li 태그를 사용해서 list의 요소들을 한 줄씩 화면 띄워보겠습니다.
  
---

- u 태그 안에 li 태그들을 넣으면 목록 형태로 요소들을 보여줄 수 있습니다.
- list.map() 안을 보시면 화살표 함수가 있습니다. 두 개의 인자가 있는데, 첫 번째 인자는 현재 요소, 두 번째 인자 는 현재 요소의 index를 가리킵니다.
- 각 li 태그의 내용은 item(각 배열 요소), 그리고 각 li 태그의 Key는 index(해당 배열 요소의 인덱스)로 줍 니다.

![image](https://github.com/user-attachments/assets/69d84c8d-9492-44b8-9e94-019e99a27473)
- 실행해보면, '추가' 버튼을 누를 때마다 한 출씩 목록 형태로 출력되는 것을 볼 수 있습니다.

---

#### 3. list의 요소들을 한 줄씩 출력하기
- 목록의 각 계획을 완료했다면, 완료했다는 의미로 취소선을 그을 수 있어야 합니다.
- 만약 어떤 계획을 삭제하고 싶다면, 그 계획을 목록에서 제 거할 수 있어야 합니다.
- 목록의 각 요소를 클릭하면, 취소선이 생기거나 사라지게 하기 위해 onclick 이벤트를 이용합니다.
- 목록의 각 요소를 더블 클릭하면, 그 요소가 목록에서 사라 지도록 onDoubleclick 이벤트를 이용합니다.

- 목록의 각 요소에 onClick 이벤트가 발생하 면 handleStrikeThrough 함수를 실행
- `handleStrikeThrough` : 해당 요소에 취소 선이 있으면 제거, 그렇지 않으면 취소선 추
가
- 목록의 각 요소에 onDoubleClick 이벤트가 발생하면 handleDelete 함수를 실행
- `handleDelete` : 해당 요소의 index를 인자로 받아서, 그 index에 있는 요소를 제거한 새로운 배열로 list를 업데이트

![image](https://github.com/user-attachments/assets/b455771a-d101-48d0-896f-b26de15e20e3)

---

### 📢과제
실습 결과 캡쳐 후 노션에 업로드하기(4차시 자료 참고)

👉 6기 노션 > SW과제제출 > React.js > 해당 차시 > 본인이름 > 과제제출란

👉 [6기 SW 과제제출 링크](https://www.notion.so/SW-8502eeef321b43e2ad13ece0f626be33)
