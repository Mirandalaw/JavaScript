# JavaScript - Node.js

: 자바스크립트의 동시성 모델 
   - event loop, call stack, callback queue
   
  -Event loop, Main Thread
    - 여러 스레드를 사용
   
    - 우리가 작성한 코드가 실행되는 스레드를 메인 스레드라 부름
   
    - 한 Node.js 프로세스에서 메인 스레드는 하나이며, 한 순간 한 줄씩만 실행함
   
    - 그러나 그 외의 일(file I/O, network---) 을 하는 워커 스레드는 여럿이 있을 수 있음.

  -Call Stack 
   ```function f3() {}
      function f2() { f3() }
      function f1() { f2() }
      f1()
   ```      
     콜 스택이란, 지금 시점까지 불린 함수들의 스택임.
     함수가 호출될 때 쌓이고, 리턴할 때 빠짐.
     
     
  -Callback Queue
     - 콜백 큐(메세지 큐)는 앞으로 실행할 콜백(함수와 그 인자)들을 쌓아두는 큐임.
     
     - 콜백은 브라우저나 Node가 어떤 일이 발생하면(event) 메인 스레드에 이를 알려주기 위해(callback) 사용됨.
     
      * 이벤트는 파일 처리의 완료, 네트워크 작업의 완료, 타이머 호출 등이 있습니다.
    
    > ex1)
    
    ```console.log('1')
    
       setTimeout(() => {
         console.log('2')
        },0)
        
       console.log('3')
     ```
     
       ==> 1,3,2 로 출력되어짐
       
    > ex2)
    
    ```setInterval(() => {
         console.log('Hey!')
         while(true) {}
        }, 1000) ```
        
        5초 동안 메세지는 몇 번이나 출력되는 것이 맞을까요?
        
        ==> 1번입니다. while loop를 도는 동안 call stack이 절대 비지 않기 때문입니다.
            이 동안은 callback queue에서 콜백을 꺼낼 수가 없기 때문에, setInterval이 아무리 콜백을 쌓아도 메인 스레드에서 실행될 수가 없음.
            이런 경우를 event loop를 block 한다고 함.
             **최대한 피하는 것이 좋음**
