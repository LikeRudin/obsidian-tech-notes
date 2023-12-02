
프론트엔드에서 백엔드로 HTTP 요청을 보낼때, Get 이 아닌 다른 HTTP 메서드를 사용하려면 fetch의 2번째 인자로 다음과 같은 설정 객체를 전송해야한다.

```json

{
method: "POST"
body: JSON.stringify(body),
header: {"Content-Type": "Application/JSON"
		}}
```