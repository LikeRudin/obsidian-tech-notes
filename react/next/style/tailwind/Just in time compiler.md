

프로젝트에 필요한 스타일을 직접 생성한다

Tailwind 3.0 이전까지는 실제로 엄청 거대한 CSS 파일을 생성하고,

20만줄이상의 거대한 calss 정의파일을 가져와서 개발단계에서 사용하였다.

하지만 3.0이후에는 컴파일러가 className을 tailwind의 규칙에 맞춰서 해석한 후
css style 코드를 생성해준다.

Just in time compiler 덕분에 tailwind package가 굉장히 가벼워졌고,
사전에 정의하지 않은 구체적인 값을 입력하여 사용 할 수있게되었다.

```css
bg-[url(vercel.svg)]
text-[97851]
text-[#000]
```