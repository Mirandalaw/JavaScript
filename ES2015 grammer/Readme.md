#*ES6*

 - 최신 명세 : https://tc39.github.io/ecma262/
 
 - 브라우저별 기능 개발 현황 : http://kangax.github.io/compat-table/es2016plus/

 ※ 최신 버전의 JaveScript를 지원하지 않는 브라우저가 항상 존재함
 
   - 이러한 문제를 해결 하기 위해, transpiler 와 polyfill 두 가지 도구를 사용
      1. transpiler
        
         - 최신 버전의 JavaScript의 문법을 똑같이 동작하는 이전 버전 JavaScript의 문법으로 바꾸어 주는 도구
         - 개발자는 최신 버전으로 코딩하고, 실제로 사용자에게 배포할 코드는 구형 브라우저에서도 잘 동작하도록 변환해주는 것
         
         ex) Babel, TypeScript
      
      2. Polyfill
         - JavaScript를 실행하는 구동 환경에는 여러 가지 문법과 기능이 추가됨
         - 이를 구형 환경에서도 사용할 수 있도록 똑같이 구현해놓은 라이브러리를 polyfill 혹은 shim 이라고 부름
         
         ex) Fetch API를 활용한 웹사이트
         

## *1. 변수(let과  const)* 
   -호이스팅(hoisting)으로 인한 꼬임 현상 방지를 위해 let/const 사용 


## *2. 화살표 함수(Arrow Function)*

  ```var elements = [
    'hydrogen',
    'helium',
    'lithium',
    'beryllium'
]

//이 문장은 배열을 반환함 : [8, 6, 7, 9]
elements.map(function (element) {
    return element.length;
});

//위의 일반적인 함수 표현은 아래 화살표 함수로 쓸 수 있다.
elements.map((element) => {
    return element.length;
}); //[8, 6, 7, 9]

elements.map(element => {
    return element.length;
}); //[8, 6, 7, 9]

// 화살표 함수의 유일한 문장이 'return'일 때 'return'과
// 중괄호 ({}) 를 생략할 수 있다.

elements.map(element => element.length); // [8, 6, 7, 9]

// 이 경우 length 속성만 필요하므로 destructuring 매개변수를 사용할 수 있다.
// 'length'는 우리가 얻고자 하는 속성에 해당하는 반면,
// lengthFooBArX'는 변경 가능한 변수의 이름일 뿐이므로
// 원하는 유효한 변수명으로 변경할 수 있다.

elements.map(({ length: lengthFooBArX }) => lengthFooBArX); // [8, 6, 7, 9]

// destructuring 파라미터 할당도 아래와 같이 작성할 수 있습니다.
// 이 예에서 정의한 객체내의 'length'에 값을 지정하지 않은 점에 주목하세요. 대신, "length" 변수의
// 리터럴 이름은 우리가 해당 객체에서 꺼내오고 싶은 속성이름 자체로 사용됩니다.

elements.map(({ length }) => length); // [8, 6, 7, 9] 
```
 -> 참고 : https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Functions/Arrow_functions
## *3. 나머지 매개변수(Rest Parameters)*



## *4. 분해대입(Destructuring Assignment)*


