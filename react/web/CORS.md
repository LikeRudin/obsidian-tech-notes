
Cross Origin Resource Sharing (CORS)


서로 다른 출처에서 데이터를가져오는것
원칙적으로, 다른 출처에서데이터를 요청하면 Block 된다.

그러므로 프론트와 서버 구성을 다르게 해줄경우,

Proxy 설정을 해야한다.


package.json

```
proxy: "api요청을 처리하는 서버주소"
```
Vite.Config.ts

```json
  
export default defineConfig({

  server: {
    open: true,
    // 현재 frontend Port
    port: PORT,
    proxy: {
      '/api': {
      // 바꿔줄 주소
        target: API_BASE_URL,
        changeOrigin: true,
        ws: true,
        rewrite: (path) => path.replace(new RegExp(`^${API_PREFIX}`), ''),
      },
    },
  },
});
```