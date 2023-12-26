

처음에는 type check에만 집중했습니다.

리액트 쿼리를 사용할때, typescript 보호를 제대로 적용하기위해서는 
QueryFn 혹은 MutationFn에 타입을 주어야 합니다.

그래서 MutationFn에 다음과 같이 타입을 주었습니다.

```ts
// T: Post할 데이터 타입
// R: 서버에서 받는 데이터 타입

export const joinAPICall = async <T, R = any>(variable: T): Promise<R> => auth.post(URLS.API.AUTH.JOIN, variable);

```

그런데 async 로 타입을 주면, 굳이 반환타입으로 Promise type을 주지않아도 자동으로 반환 타입이 Promise로 적용됩니다.

```ts
export const join = async (joinForm: IJoinForm) =>
client.post(URLS.API.AUTH.JOIN, joinForm);
```

그리고 또, 처음의 joinAPICall에서는 axios의 호출 주소가 명확하게 바인딩 되어있으므로, 굳이 <T,R>과 같은 generic으로 타입을 만들어줄 필요가 없습니다.

 
 저렇게 구체적인 함수 말고, 
 이렇게 추상 타입으로 분류 해주는 게 좋은 것 같습니다.
```ts
type MutationFn = <T, R = any>(variable: T) => Promise<R>
```



```ts
import { useMutation } from '@tanstack/react-query';
import { joinAPICall } from '@/apis';

interface IUseJoinMutationParams {
	emails: string;
	password: string;
	name: string;
}

export const useJoin = () => {
	return useMutation({
		mutationFn: joinAPICall<IUseMutationParams>
	});
}

import { useNavigate } from 'react-router'; 
import { AxiosError, AxiosResponse } from 'axios';
import { useMutation } from '@tanstack/react-query'; 
import { join } from '@/apis'; 
import { IErrorResponse, IJoinForm } from '@/types';
import { URLS } from '@/constants'; 

export const useJoin = () => {
const navigate = useNavigate(); 
const { mutate } = useMutation< AxiosResponse<any>, AxiosError<IErrorResponse>, IJoinForm >({
	mutationFn: join,
	onSuccess: () => { 
		alert('회원가입 성공!!');
		navigate(URLS.CLIENT.HOME); }, 
	onError: (error: AxiosError<IErrorResponse>) => {
		const message = error.response?.data.message;
		alert(message || '회원가입 중 오류가 발생했습니다.'); 
		}, 
	});
return { mutate }; 
};
					

// 컨벤션, 코드정리
// - util함수: 타입을 
// - 코드 중복: 타입 재사용
// 
// import 문을 상하로 
// react
// 다른 라이브러리
// 우리 컴포넌트
// props는 별일없으면
```
