

profile page에서 만듣 각각의 api에서 나오는 것들을 만들어서 뿌려준다.


product-list를 따로 하나의 component로 분리하는것이 좋다

왜냐면 Fav, sales, purchases를 전부다 다른 것으로만ㄷ르어주는것은상당히 불합리하기 때문이다


```jsx
<ProductList kind="enum"/> 
```