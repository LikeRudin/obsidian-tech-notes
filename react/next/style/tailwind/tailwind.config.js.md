


테일윈드를 설정하는 파일

```node
// 설치
npm install -D tailwindcss postcss autoprefixer

// tailwind.config.js 생성
npx tailwindcss init 
```

예시 설정
```js
module.exports = {
  // tailwind css classname을 사용할 파일경로 지정
  content: [
    "./pages/**/*.{js,jsx,ts,tsx}",
    "./components/**/*.{js,jsx,ts,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
  // media: mediaQuery 브라우저의 설정을따라감
  // class: className 일경우 단순 클래스이름을 부여함
  // html 태그에 className dark 를 부여하거나 해제하는 방식으로 컨트롤 한다.
  darkMode: "media" | "class "
};
```