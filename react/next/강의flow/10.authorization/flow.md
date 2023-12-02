
유저의 로그인 여부를 확인하는 useUser 훅을 작성


`useSWR` `stale while revalidation` 기술을 사용한다.

- 핵심기능: useSWR은 fetch해온 데이터를 캐싱한다. 그 후 재요청을 보낼때 기존 데이터와 비교하여, 변경사항이없다면 데이터를 교체하지 않는다. 즉 화면이 더 부드럽게 남아있는다.

- 1번인자로 URL 2번인자로 fetcher 함수를 받는다.

- SwrConfig 라는 Wrapper로 _app 컴포넌트를 감싸서 fetcher를 제공해줄 수있다



이제부터 항상 모델을 생성하고, prisma db를 업데이트하고, useMutation hook, useSWR 을 설정해주는 순서로 작업할것이다.