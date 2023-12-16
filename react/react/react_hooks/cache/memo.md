
memo를 사용하면 컴포넌트의 props가 바뀌지 않았을때 
re-rendering되는것을 막을 수 있다.

```js

'use client';

function WeatherReport({record}) {
	const avgTemp = calculatingAvg(record);
	//...
}

const MemoWearherReport = memo(WeatherReport);

function App() {
const record = getRecord();
return (
	<>
	<MemoWeatherReport record={record} </>
)
}


```