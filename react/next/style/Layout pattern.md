
Next에선 pug와 마찬가지로 Layout역할을 컴포넌트를 만들 수있습니다.
주로 공통된 Header 및 footer를 정의하는데 사용됩니다.

만약 모든 페이지에서 단일 Layout을 사용하고 싶다면 [[[custom app]]] 의 `_app.js` 에 Layout을 작성하는것을 추천합니다.

```js
export default function Layout ({children}) {
<Header></Header>
{...children}
<Footer></Frooter>
} 
```