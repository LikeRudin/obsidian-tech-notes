
cache를사용하면 여러 작업을 memoize 하고, 
컴포넌트간에 공유할 수 있다.

```jsx

'use client';

const cachedFetchReport = cache(fetchReport)

function WeatherReport({city}) {
	const report = cachedFetchReport(city);
	//..
}

function App() {
	const city = "Los Angeles";
	return(
	<>
		<WeatherReport city={city}/>
		<WeatherReport city={city}/>

	</>)
}

```