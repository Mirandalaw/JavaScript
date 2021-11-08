# JavaScript - Node.js

: 자바스크립트의 동시성 모델 
   - event loop, call stack, callback queue
   
   
  -Event loop, Main Thread model
   : 여러 스레드를 사용
   : 우리가 작성한 코드가 실행되는 스레드를 메인 스레드라 부름
   : 한 Node.js 프로세스에서 메인 스레드는 하나이며, 한 순간 한 줄씩만 실행함
   : 그러나 그 외의 일(file I/O, network---) 을 하는 워커 스레드는 여럿이 있을 수 있습니다.

  -call stack 
   ```function f3() {}
      function f2() { f3() }
      function f1() { f2() }
      f1() ```
      
     1. 콜 스택이란, 지금 시점까지 불린 함수들의 스택임
     
     2. 함수가 호출될 때 쌓이고, 리턴할 때 빠집니다.
       
