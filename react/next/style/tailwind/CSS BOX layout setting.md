

Border:  border 
padding : p
margin: m

각방향은 r l t b를 붙여서 표시
좌우는 x, 상하는 y로 표시

음수값을 주고싶다면 `-` 를 맨 앞에 붙여준다

```css
p-6 => padding 6

-p-6 => padding -6
```


Flex layout 자식요소에게 margin을 주고싶다면 space,
Grid의경우에는 gap을 사용한다.


flex를 사용한다면
flex flex-col
과 같이 flex 자체와 옵션은 따로 선언해주자

자식 크기가 변할 수있다.



최상단 div에 px를 부여하면

여러가지 컴포넌트에대한 구분선을 위해 부여한 border-b가 가로 끝까지 나가지 않는 모습을 볼수있다.

그러므로 px를 하단의 컴포넌트에 구현하거나, 

`divide-y-[1px]`이라는 유틸리티 클래스네임을 사용한다

형제관계가있다면 사이에 border를 그려주는 역할을 한다.

flex-row-reverse를 통해서 내 메시지와 남의메시지를 구분할 수있다.


텍스트가 Box 밖으로 안나오게 하려면 break-normal등을 이용하면된다.