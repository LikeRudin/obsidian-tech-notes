


api나 db로부터오는 외부이미지가 아니라, server내부에 저장되어있는 이미지를 뜻한다.

앞서말한 lazy-loading 이나 place-holder가 바로 
local Image를 위한기능이다.


placeholder="blur" 옵션 제공시, gif 압축 blurr 이미지가 먼저 보여진 후
로드가 완료되면 _next 로 시작하는 이미지를 제공해준다.

```js
import Image from "next/image"
```

quality 옵션으로 제공하고싶은 이미지의 퀄리티를 정할 수있다.



