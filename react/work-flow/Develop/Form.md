
정의 

사용자로부터 입력받은 데이터를 처리하는  HTML Element이다.

### 구성요소
	- HTML Element
		- input
		- form
	- Form validation
		- submit의 유효성을 검증할 로직 혹은 도구
	- Fetch with api
		- submit이 유효할 때, 서버의 통신을 위한 로직
	 - After Fetch
		 - 통신 결과를 처리하는 로직


### Work Flow

1.  form 구상하기
	- form의 목적에 맞게 
	- 필요한 Input의 종류
		- 필수 / 비 필수
1.  구성요소 디자인
	 - 사용하는 툴을 이용해 구성요소를 디자인
2.  Form validation 로직추가
	- 적절한 값을 입력했는지 확인하는 로직을 추가한다.
3.  submit handler 추가
	 - 유효한 값이 입력될시, submit을 처리하는 로직을 추가
4. after submit
	- 통신 결과를 처리하는  로직을 추가한다.
5. 테스트하기
	- 정상적으로 작동하는지 테스트한다. 


