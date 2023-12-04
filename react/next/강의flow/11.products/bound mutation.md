
목적: 다른 useSWR hook에서 나온데이터를 다른곳에서 똑같이 mutate 하는 방법 습득


{}=useSWRConfig()

화면에서 얻은 데이터만 바꾸기원한다면 boundMutate (useSWR의 반환값) 사용

다른 화면에서 얻은걸 사용하려면 unBoundedMutate (useSWRConfig의 반환값 사용)







useMutation

유저정보
<유저정보>useMutation(쿼리 api주소, HTTP메서드 종류 ) => [trigger, data]
{axios}
















