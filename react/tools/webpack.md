
Javascript bundling tool

FrontEnd 영역의 Javascript 코드를 압축해서 용량을 줄여주는 역할을 한다.

압축 과정에서 여러가지 규칙(`rules`)을 적용하여
입맛에 맞는 파일을 얻을 수있다.

ex) JS 버전 다운그레이드, SCSS를 일반 CSS로 변경 등




## 설정 요소

루트 디렉토리의 `webpack.config.js` (webpack.config.ts) 
파일을통해 작동을 설정한다.

- entry와 output은 필수로 설정해야 한다.

### entry
- 변환할 파일

### mode
- process.env.NODE_ENV의 값을 설정
- string = 'production': 'none' | 'development' | 'production'

### watch
- 자동으로 번들링을 실행하는것

### output
- 변환 결과
- properties
	- filename: 변환결과 파일 이름
	- path: 변환결과가 저장될 `절대경로`
	- clear: boolean 번들링 작업전에, 기존 번들링 파일 삭제

### module.rules[](https://webpack.kr/configuration/module/#modulerules)

특정 모듈별로 처리 규칙을 저장하는 배열
`test`와 `use` 를 포함하는 객체를 성분으로 갖는다.

test 
- 적용할 파일의 확장자명
use
- 규칙 loader를 묘사한 객체 혹은배열
- 배열일경우 적용순서는 역순이다.
### keywords

코드압축
번들링도구
loader
rules