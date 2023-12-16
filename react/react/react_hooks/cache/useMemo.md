https://react.dev/reference/react/cache#cache-memo-usememo

State가 아닌 방식으로 변수를 저장하기위해 사용한다.
Rendering 과정동안, 비싼 비용의 계산을저장하는등을할 수있다.

```jsx
'use client';

function ExampleUseMemo = ({record}) {
	const avgTemp = useMemo(() => calculateAvg(record)),record);
}

function App() {
	const record = getRecord();
	return(
	<>
		<ExampleUseMemo record={record}/>
		<ExampleUseMemo record={record}/>
	</>
	 )
}

```
위의 코드에선 `ExampleUseMemo`가 두개지만, useMemo Hook은 각각 Component Local에 저장되기때문에, cache가 공유되지 않는다.