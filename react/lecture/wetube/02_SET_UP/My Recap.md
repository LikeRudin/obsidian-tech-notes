  
제 2장 Setup 파트에서는 프로젝트를 만들고 개발을 위한 환경을 설정했습니다.

# Work

### 1.  프로젝트 초기화 및 git hub와 연결


1. 깃허브에서 원격 repository 생성
2. 프로젝트에서 연결
git init 
git remote add origin <>
3. 프로젝트 초기화
npm inint

### 2. 개발에 필요한 의존성 설치

```js
npm install express

npm install @babel/node --save-dev
npm install @babel/core --save-dev
npm install @babel/preset-env --save-dev 

npm i nodemon --save-dev

```

그리고 개발에서 사용할 `express`, `nodemon`, `babel` 등을 설치하면서
package.json의 `dependencies`와 `devDependencies`에 대해 배웠습니다.

`dependencies`를 한국어로 직역하면 "의존성"으로, 우리 프로젝트가 사용 중인, 혹은 필요로하는  패키지 목록을 저장하는 곳입니다.

`npm install` 명령어로 패키지를 설치하면, 해당 패키지는 자동으로 `package.json`의 `dependencies`에 추가되며,
 `--save-dev` 플래그를 사용하면 `devDependencies`에 추가됩니다.


"개발 편의를 위해 필요하지만 실제 프로그램에는 필요없는것들"은 devDependencies로 저장합니다.

### 3. babel preset 설정

설치한 babel의  플러그인을 사용하기위해
babel.config.json  파일을 만들어 다음 코드를 입력해주었습니다.

```json
{
	"presets": ["@babel/preset-env"]
}

```

### 4. scripts 명령어 설정


```json
"scripts": {
	"dev" : "nodemon --exec babel-node index.js"
}
```
scripts는 우리가 터미널에서 사용할 명령어를 저장하는곳입니다.
`npm run <저장된명령어>` 로 실행할 수있습니다.

위와 같은 값을 갖는 package.json이 있는 경로에서
`npm run dev` 명령어를 호출하면

`nodemon --exec babel-node index.js`를 실행합니다.

이 명령어 조합을 해석해보면 다음과 같습니다.

nodemon --exec :파일이 수정될때마다, 뒤에 오는 명령어 실행
babel-node : 뒤에오는 파일을 babel-node로실행
index.js : 실행할 js 파일

즉, 위의 명령어를 사용하면 
파일이 수정될때마다 babel-node로 index.js 파일을 실행하게돕니다.
