# GET IT SW교육 React.js
## 7차시_조건부 렌더링, 라우팅
> 기간 : 24.11.06~24.11.10

### 🗂️7차시 자료🗂️
[React.js 7차시 자료](https://github.com/getit-knu/Get-React.js/blob/main/7%EC%B0%A8%EC%8B%9C/GETIT%20SW%20%EA%B5%90%EC%9C%A1%20react%20_%207%EC%B0%A8%EC%8B%9C.pdf)

👉자료를 다운 받은 후 수강해주세요!

### 🎞️7차시 강의🎞️
[![Video Label](http://img.youtube.com/vi/u8npIqhcjhE/0.jpg)](https://youtu.be/u8npIqhcjhE)

👉위 이미지를 누르면 강의를 들을 수 있습니다.

---

### 🚀목차🚀
1. 미니 블로그 설계
2. 라우팅 구현
3. 컴포넌트 만들기

---

#### 01.🖥️ 미니 블로그 구조
#### 🛠️ 미니 블로그 기능
![image](https://github.com/user-attachments/assets/6fea9826-3ff2-47e2-b6af-f7456488b519)
- ⚡**상단바**
  - **블로그 이름**이 있고 그 옆에 다른 페이지로 이동하는 메뉴 버튼들이 있음(Home, 글쓰기)
  - 'Home' 버튼을 누르면 홈 페이지로 이동
  - '글쓰기' 버튼을 누르면 글쓰기 페이지로 이동
<br/>

![image](https://github.com/user-attachments/assets/d4cde463-c56c-4bea-bc1e-46f70b058e15)
- 🏠**홈 페이지**
  - 제목과 대략적인 내용이 보이는 상자 형태로 나열된 게시물들
  - 게시물 박스를 누르면 해당 게시물에 대한 게시물 페이지로 이동
<br/>

![image](https://github.com/user-attachments/assets/666ba7f7-40e2-46f9-945f-113cb5af2d26)
- 📰**게시물 페이지**
  - 게시물을 볼 수 있음
  - '수정' 버튼을 누르면 글 수정 페이지로 이동
  - '삭제' 버튼을 누르면 삭제 후 홈 페이지로 이동
<br/>

![image](https://github.com/user-attachments/assets/06ced602-adf3-401b-b247-639627f2c50c)
- ✍️**글쓰기 페이지**
  - 제목, 내용을 입력할 수 있음.
  - '저장' 버튼을 누르면 게시물이 추가되고 홈페이지로 이동
  - '취소' 버튼을 누르면 이전 페이지로 돌아감

- 🪚**글 수정 페이지**
  - 제목, 내용을 수정할 수 있음
  - '저장' 버튼을 누르면 게시물이 수정되고 홈페이지로 이동.
  - '취소' 버튼을 누르면 이전 페이지로 돌아감
<br/>

#### ⬇️ 게시물을 저장하는 방법
- `localStorage` 사용하기
  - 웹 브라우저에서 제공하는 간단한 키-값 쌍의 데이터 저장소
- **데이터 저장** - localStorage.setItem('key', 'value');
- **데이터 불러오기** - const value = localStorage.getItem('key');
- **데이터 삭제** - localStorage.removeltem('key");
- **모든 데이터 삭제** - localStorage.clear();
- localStorage에 정보들을 저장해둔다면, 리액트 애플리케이션을 껐다 켜도 게시물들은 그대로임.
  
---

#### 02. 🌟라우팅 구현
#### react-router-dom 설치 및 사용
- 설치 : npm install react-router-dom --save
- 사용
  - `BrowserRouter`
    - index.js에서 App 컴포넌트를 감싸도록
    - `index.js` 는 강의 및 강의자료 참고
      
  - `Routes, Route`
    - 페이지 바뀌는 건 Main 컴포넌트에서 구현하기로 함
    - Main에서 Routes, Route 불러와서 사용하기
    - `Main.js`는 강의 및 강의자료 참고
      
  - `useNavigate`
    - 상단 바에 있는 버튼들을 누르면 페이지가 바뀌게 할 것임
    - TopBar 등에서 useNavigate 불러와서 사용하기
    - `TopBar.js`는 강의 및 강의자료 참고

---

#### 03. 🌟컴포넌트 만들기
#### 컴포넌트들
- Componets
  - `TopBar` : 상단 바
  - `Main` : 라우팅 구현
  - `PostBox` : 홈 화면에서 각 게시물을 보여줄 양식

- Pages
  - `Home` : 게시물들이 나열되어있는 페이지
  - `CreatePost` : 게시물을 작성하는 페이지
  - `PostPage` : 게시물을 확인하는 페이지
  - `UpdatePost` : 게시물을 수정하는 페이지

- 자세한 코드는 강의 및 강의자료 참고


#### 미니 블로그 결과
#### 🏠 Home 페이지
![image](https://github.com/user-attachments/assets/78e1a40a-ff56-4a0e-8d0f-ef516598d921)

#### 🧑‍💻CreatePost 페이지
![image](https://github.com/user-attachments/assets/81233488-f494-48c8-8a34-44b737cd4acd)

#### ✍️ PostPage 페이지, UpdatePost 페이지
![image](https://github.com/user-attachments/assets/a5a74c34-6e3a-4fb1-a0af-394242d7b54d)

---

### 📢과제
실습 결과 캡쳐 후 노션에 업로드하기(6차시 자료 참고)

👉 6기 노션 > SW과제제출 > React.js > 해당 차시 > 본인이름 > 과제제출란

👉 [6기 SW 과제제출 링크](https://www.notion.so/SW-8502eeef321b43e2ad13ece0f626be33)
