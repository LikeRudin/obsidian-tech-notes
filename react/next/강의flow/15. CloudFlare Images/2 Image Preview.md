
1. name="avatar" type="flie"인 input을 새로 만든다.
2. onValid로 다루는 데이터에 avatar를 추가한다.
3.  watch("avatar")로 input을 관리한다
4. URL.createObjectURL(file) 을통해 avatarfile의주소를 추출한다.
5. 해당 주소를 avatarState에 저장하여, avatar의 preview를 보여준다.
6.
useState로 avatar를 관리

useForm의 watch를 사용한다.

watch 는 일종의 이벤트핸들러이다.

const avatar = watch()

URL.createObjectURL(file) => file의 url을 출력해준다.
blob을 포함한 모든 주소를 입력하면 사진을 볼 수있다.

