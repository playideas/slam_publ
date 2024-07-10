# 코드 가이드

## Creating a project

```bash
git clone https://github.com/playideas/slam_publ.git my-app

npm install
```

## Developing

```bash
npm run dev
```

## Tech Stack

- Sveltekit
- TypeScript
- Sass

## Folder Structure

📦src  
 ┣ 📂lib  
 ┃ ┣ 📂components  
 ┃ ┃ ┣ 📂account  
 ┃ ┃ ┃ ┣ 📂signin  
 ┃ ┃ ┃ ┃ ┗ 📜Step1.svelte  
 ┃ ┃ ┃ ┗ 📂signup  
 ┃ ┃ ┃ ┃ ┗ 📜Step1.svelte  
 ┃ ┃ ┣ 📂common  
 ┃ ┃ ┃ ┗ 📜Modal.svelte  
 ┃ ┃ ┗ 📂layouts  
 ┃ ┃ ┃ ┗ 📜MainHeader.svelte  
 ┃ ┗ 📂utils  
 ┃ ┃ ┗ 📜index.ts  
 ┣ 📂routes  
 ┃ ┣ 📂(account)  
 ┃ ┃ ┣ 📂signin  
 ┃ ┃ ┃ ┗ 📜+page.svelte  
 ┃ ┃ ┣ 📂signup  
 ┃ ┃ ┃ ┗ 📜+page.svelte  
 ┃ ┃ ┗ 📜+layout.svelte  
 ┃ ┣ 📜+layout.svelte  
 ┃ ┗ 📜+page.svelte  
 ┣ 📂stores  
 ┃ ┗ 📜index.ts  
 ┣ 📂styles  
 ┃ ┣ 📜main.scss  
 ┃ ┗ 📜reset.scss  
 ┣ 📂types  
 ┃ ┗ 📜index.ts  
 ┣ 📜app.d.ts  
 ┗ 📜app.html

### Description

#### lib/components

> 재사용 가능한 컴포넌트들이 위치하는 폴더

- lib/components/layouts
  - 헤더, 사이드바, 콘텐츠 영역, 푸터 등과 같은 주요 레이아웃 요소들을 관리
- lib/components/common
  - 공통으로 사용되는 Modal, DropDown 등과 같은 사용자 인터페이스 요소들을 포함
- lib/components/기타
  - 해당 페이지에서 사용하는 컴포넌트
  - ex) lib/components/account/signup - 회원가입 페이지에서 사용되는 컴포넌트 모음
  - ex) lib/components/account/signin - 로그인 페이지에서 사용되는 컴포넌트 모음
  - ex) lib/components/home - 메인 페이지에서 사용되는 컴포넌트 모음

#### lib/utils

> 정규표현식 패턴이나 공통함수 등 공통으로 사용하는 유틸 파일들이 위치하는 폴더

#### stores

> 상태 관리를 위한 폴더

#### styles

> 공통으로 사용되는 css 파일들이 포함되는 폴더

- 공통으로 사용 안 되는 것은 해당 페이지나 컴포넌트에 직접 css 작성

#### types

> 타입을 정의한 폴더

## Coding convention

### 💡 **폴더명, 파일명 규칙**

- **폴더명과 파일명**은 [**카멜 케이스**]로 생성
- **단, 컴포넌트와 타입을 정의하는 파일명**은 [**파스칼 케이스**]로 생성

### 🐪 **함수명, 변수명은 [카멜 케이스]로 작성합니다.**

```js
let isTouch = false;

const handleMouseDown = (e) => {
  ...
};
```

### 🐫 **컴포넌트, 타입명, 클래스는 [파스칼 케이스]로 작성합니다.**

```tsx
// Component
function App({ count }: Props) {
	return <div>{count}</div>;
}

// Type
interface Props {
	count: number;
}

type Tool = 'select' | 'move';

// Class
class Car {
	private model;
	constructor(model) {
		this.model = model;
	}
}
```

### 🥊 **상수는 [어퍼 케이스](https://www.notion.so/Coding-convention-277187ddbab147069735d02f7202bc6c?pvs=21)로 작성합니다.**

```js
const minScale = 0.1; // bad
const MIN_SCALE = 0.1; // good
```

- **값이 변하지 않는 변수는 `const`, 값이 변하는 변수는 `let`을 사용합니다.
  `var`는 절대로 사용하지 않도록 합니다.**

### ✔️ **Boolean type은 is로 시작합니다.**

```js
let isAvailable = false;
```

### ✔️ **함수명은 동사+명사로 작성합니다.**

```js
function getUserInformation(){
  ...
}
```

### ✔️ **들여쓰기는 공백 문자 2개를 사용합니다.**

```jsx
// good
function sum(x, y) {
	const result = x + y;
	return result;
}
```
