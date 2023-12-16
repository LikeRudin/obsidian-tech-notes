

1. I/O 작업은 느리다.
2. I/O 에대해 논-블로킹 방식의 시스템을 사용한다.
3. busy-waiting은 여러모로 비효율적이다.
4. event demultiplexer 패턴을 사용한다.

이것을 종합하여, I/O요청 및 이벤트 핸들러를 보관하는 `app`과
I/O를 해석해서 event를 생성하는 `event-demultiplexer`
그리고 생성된 event를 처리하면서 이벤트 핸들러의 호출시마다 app에 제어권을 위임하는 `event-loop` 이렇게 삼신기의 조합이 
리액터 패턴이다.


https://www.geeksforgeeks.org/what-is-reactor-pattern-in-node-js/