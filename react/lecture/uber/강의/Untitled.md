# Contents


Webpack을 활용해서 SCSS로 작성한 특수 CSS를
Brower가 이해할수있는 일반 CSS로 변형시킨다.

# Tools &  Keywords

CSS, SCSS

sass-loader

특수 CSS를 일반 CSS로 변환

# Works

1. scss 폴더 생성

```js
// client/scss/_variable.scss
$red: red;

//client/scss/styles.scss

@import "./_variables";

body {
  background-color: $red;
  color: white;
}

```

2. 의존성 추가: sass, sass-loader, css-loader, style-loader
```json
npm install sass sass-loader css-loader style-loader -D
```

3. webpack.config.js의 module에 scss 설정 오브젝트 추가
```js
 module:{ rules: [
 //...
	 {
		 test: /\.scss$/,
		 use: ["style-loader", "css-loader", "sass-loader"],
	 }
	 ]}
```

# Explanations

webpack의 rules에서 use를 배열로 선언하여 
여러개의 `loader`를 적용시켜줄 수있다.

이때, loader는 배열성분의 역순으로적용된다.
```js
 ["style-loader", "css-loader", "sass-loader"]
```

sass-loader -> css-loader -> style-loader
순으로 적용된다.
# RoadMaps