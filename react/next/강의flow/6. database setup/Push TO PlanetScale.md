

우리가 하나의 데이터 객체를 다른 객체에 연결하려 할때, 
대상을 식별하기위해 사용하는것은 대상의 Id로, Foriegn key라 한다.

그런데 우리가 입력한 key를 갖는 대상이 실존하는지에대한 검증을 할필요가있다.참조 무결성 Referential integrity을 체크해야한다.

그것에대한 도움을 prisma에게 받기 위해 다음 코드를 입력한다.


```js
datasource db {
relatioMode ="prisma"
}
```

[[error] prisma db push 중 오류 (velog.io)](https://velog.io/@rlorxl/prisma-db-push-%EC%97%90%EB%9F%AC-%ED%95%B4%EA%B2%B0)
```js
npx prisma db push

Environment variables loaded from .env
Prisma schema loaded from prisma/schema.prisma
Datasource "db": MySQL database "carrot" at "127.0.0.1:44503"

// 오류발생
Error: target: carrot.-.primary: vttablet: rpc error: code = PermissionDenied desc = DDL command denied to user 'planetscale-reader' for table 'User' (ACL check error) (CallerID: planetscale-reader)
   0: sql_schema_connector::apply_migration::migration_step
           with step=CreateTable { table_id: TableId(0) }
             at schema-engine/connectors/sql-schema-connector/src/apply_migration.rs:21
   1: sql_schema_connector::apply_migration::apply_migration
             at schema-engine/connectors/sql-schema-connector/src/apply_migration.rs:10
   2: schema_core::state::SchemaPush
             at schema-engine/core/src/state.rs:436
```

prisma는 dev와 production 브랜치를 구분해주어야 한다.

production에 연결후 push 해서 문제가 생겼다고한다

1. pscale branch create `db이름` `브랜치이름`

pscale branch list `db이름`
1. pscale connect `db이름` `브랜치 이름`
2. npx prisma db push


알고보니 버전 문제였다
```
  
1, 터미널에 다음 코드 입력  
~ curl -O -L https://github.com/planetscale/cli/releases/download/v0.156.0/pscale_0.156.0_linux_amd64.deb  
  
2. sudo dpkg --install pscale_0.156.0_linux_amd64.deb  
  
비밀번호 입력  
  
3. pscale 입력  
- 비밀번호 설정하라고 나옵니다.
```