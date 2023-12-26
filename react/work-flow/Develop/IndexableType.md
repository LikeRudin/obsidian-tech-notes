
특정 형식의 properties를 갖는 객체 타입을 만드는 방법

다음 순서로 Type을 만든다

## 1. 추상 타입

1. 단일 개체를 설명하는 타입 선언
2. 단일개체 타입을 값으로 갖는 인덱스 시그니처 인터페이스 선언


### 예시 

```ts
type UnitColorThemeType = {
	background:string;
	font:string;
	border:string;
}

interface IColorStyles {
	[key:string]: UnitColorThemeType
}
```

## 2. 구체타입: property 이름 정하기

utility type을 이용한다
```ts

interface CatInfo {
age: number;
breed: string;
}

type CatName = "miffy" | "boris" | "mordred";

Record<CatName, CatInfo>
```


## 3. 구체 타입: 사용할 타입 바인딩하기

그냥 key를 입력해주면 된다.

```ts

type ValidationRuleWithMessageType<T> = {
  value: T;
  message: string;
};

  type ValidationRulesType<T> = T | ValidationRuleWithMessageType<T>;

  
interface IValidation {
  required?: string | ValidationRulesType<boolean>;
  minLength?: ValidationRulesType<number>;
  maxLength?: ValidationRulesType<number>;
  pattern?: ValidationRulesType<RegExp>;
  match?: ValidationRulesType<string>;

}
```
