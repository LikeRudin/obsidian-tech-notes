

Review, sale, purchase 모델 제작


### Review

1. id/createdAt/updatedAt과같은 기본 메타정보를 준다 모두 공통이다.

2. createdBy, createdById,  createdFor, createdFor

기존과는 다르게 이번에는 최초로 User 모델을 두개 갖게된다.



리뷰를 받은유저는user.receivedReviews
리뷰를 작성한 유저는 user.writtenReviews를 통해 review목록에 접근한다.

그러므로 각 `@relation` 의 옵션으로 name을 부여한다.

Fav, sales, purchases등등은 일반적으로 Record 하나에 다 쑤셔넣는게 정상이다.

score과 같은 모델을 만들자.
