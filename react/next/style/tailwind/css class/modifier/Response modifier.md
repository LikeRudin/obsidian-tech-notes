
테일윈드는 모바일 우선 break point를 제공한다.

일반적인 방식과 다르게 모바일 화면을 기준으로 우선 디자인한 후에
desktop과 같은 커다란 화면을 위한 css 스타일을 적용해야한다. 
```
sm:
md:
lg:
xl:
2xl:
```

만약에 sm과 2xl className만 부여한다면, 2xl이하의크기는 전부 sm의 옵션을 따라간다.

sm <=> md <=> lg <=> xl <=> 2xl

각각의 className에 해당하는 css style이 다른값들을 cancel 시킨다.



반응형으로 화면이 어떻게 변하는지보고싶다면, 일단 값을 넣고, 브라우저를 통해 확인하라.