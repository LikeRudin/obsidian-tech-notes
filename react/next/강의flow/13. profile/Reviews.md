

handler를 만들기전에, score 필드를 Review 모델에 추가한다.


이미 생성된 모델에 새로운 필드를 추가하면, 마이그레이션이 필요하다.
Review 모델을 생성한후, prisma db와의 동기화도 완료했지만 이후에 새로운 필드를 추가한다면
레코드에 해당 값이없으므로 오류가 발생하게된다.

그러므로 추가 컬럼은 optional으로 설정하거나 `?`
아니면 `@default` 로 설정해주어야한다.

prisma는 default 값을 설정함으로써 마이그레이션을 마칠 수있다
기존에저장되어있던 모든 레코드들은 default로 설정한값을 갖게된다.


handler 만들기

역시 req, res를 이용한다.
`req.session.user`에있는 user정보를 꺼내와서 해당 id로 쿼리를 하는 로직을 만든다.
