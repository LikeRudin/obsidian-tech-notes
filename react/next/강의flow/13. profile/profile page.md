
역시 같다

1. useUser hook을 통해 user의 정보를 가져와 적재적소에 정보를 뿌려준다
2. 역시 data.review.map으로 review들을 뿌려준다.


조금 특별한 로직이있다면 star를 그려주는 로직이다

```js

[1,2,3,4,5].map(star => score >= star? yellowStart : grayStar)

```