
NestJS를 위한 GraphQL이 따로 존재한다.

Appolo server를 기반으로 작동한다.

GraphQL
- typeDefs
- resolvers

적용방법

code first 
- schema를 typescript가 생성함 

schema

코드
```js
//resolver 만들기

@Resolver()
export class ~~Resolver{
	@Query(() => Boolean) // return Type을 반환하는 함수
	myQueryFunction() {
	return true
	}
}

//module 만들기

// app.module

@Modue({
	imports: [
	GraphQLModule.forRoot({
	autoSchemaFile: true, // Schema file을 생성안함
	}),
	RestaurantModule,
	],
	controllers: [],
	providers: [],
})

export class AppModule
```


용어