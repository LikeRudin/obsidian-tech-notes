

### front

1. useForm을 통해 Form을 만든다.
2.  useMutation을 통해 해당 Form의 sumbit을 처리할 쿼리 함수를 불러온다.
3. useUser 훅과 useEffect를 통해  profile의 정보를 채워준다.
3.  useForm의 `handleSubmit(onValid)`의 내부에서 submit 및 redirect를 관리한다

4. 여기서 적절하지않은 phone number나 email을 입력하는경우를 방지해야한다.
	useForm의 setError를 활용한다.


당연히 useRouter를 통해서 router.replace도 사용해줘야겠지?

왜 replace냐면 뒤로가기를 제공하지 않을꺼기 때문.



enterPage를 제외하면 전부 useUser를 사용하고 있다.
_app.js에 useUserHook을 옮기는것도 괜찮은 선택이다_


### back

api를 만든다

`/api/users/me` 에 index 파일이 이미 존재한다.
우리는 수정을 위해 POST 메서드를 사용할것이므로,

withHandler의 인자에 "POST를 추가하고, 
handler의 몸체에는 req.method에 따라 다른 쿼리문 혹은 정보를 전달하는 로직을 
작성한다.

client.user.update를 사용할것

이떄, 이미 db에 저장되어있는 email이거나 phone 인지 확인하는 로직이 필요하다.
하지만, 그게 이미 사용자가 사용중인 것이면 괜찮다

그러므 if(user.session.email === req.body.email) 이면 해당 email 에대한 변경은 회피하는 방식을 사용하는게좋다.

- 만약 currentUser의 email과 현재 email이 같다면 패스
- 만약 다르다면 중복 확인 후업데이트!

- name과 같이 고유할 필요가없는값이라면, 위와같은 설명은 생략하고 업데이트 할 수있다.