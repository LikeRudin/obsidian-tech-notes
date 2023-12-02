


`/api/users/me/salse`
`/api/users/me/purchases`
`/api/users/me/reviews`

등등의 새로운 URI를 만들기위해서 폴더구조를 변경해준다.
기존의 `/api/users/me` 는 폴더로 변경해주고, index.ts 에 api 로직을 작성해준다.


기본적으로 fav와 아주 같은 로직을 따른다

1. `req.session.user` 를 통해 현재 로그인한 유저의 id를 빼낸다.
2. `await client.모델이름.findmany` 에 user id와 불러올 필드를 선택한다


위의 세개의 api및 모델은 사실 일반적으로 사용되는 패턴은 아니다

Record라는 하나의 모델안에 모든 정보를 넣어보도록 하자.