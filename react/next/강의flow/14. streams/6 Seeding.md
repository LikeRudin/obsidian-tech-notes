
seeding in prisma: creating fake data

시드는 데이터베이스에서 동일한 형태의 데이터를 일관적으로 생성하여 
애플리케이션에 필요한 데이터, 혹은 개발환경에서 필요한 mockup 데이터를 생성하는 기능이다.

`prisma/seed.ts` 에서 작업하자

client = new PrismaClient();


```json

"prisma": {
	"seed": "ts-node --compiler-options {\"module\":\"CommonJS\"} prisma/seed.ts"
}
```

`npx prisma db seed` 명령어를 통해 다음을 실행할 수있다.