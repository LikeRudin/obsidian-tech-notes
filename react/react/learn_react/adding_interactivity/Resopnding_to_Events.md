

# Adding Event Handlers


이벤트 핸들러를 추가할때에는, 반드시 "호출"하지않고
그대로 입력해주어야한다.

```js
// 올바른예시
<button onClick={() => alert('...')}/>

// 잘못된 예시
// 렌더과정에서 언제나 호출됨
<button onClick={alert('...')}/>

```


Event Propagation

이벤트가 하위 컴포넌트에서 상위 컴포넌트로 전달되는것을 막을 수있다.
Stopping Propagation
```js

e.stopPropagation() stops the event handlers attached to the tags above from firing
e.preventDefault(): prevent the default browser behavior
```