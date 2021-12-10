1.  Node.js 설치하기
   
   - nodejs.org/ko/
   - version 관리 tool
       
       : nvm(Node Version Manager)
       
       : tj/n (Node version management)

2. 개발환경 설정

   1) npm(nodepackagemanage)
      
      : 작업하고 있는 프로젝트가 npm이 관리하고 있는 패키지라는걸 알려줘야함 (package.json만들기)
            
            npm init -y
          
   
   2) IDE에서 제공해주는 것

      : Formatting : Prettier
      
         1. maketplace 에서 prettier 설치
        
         2.  ```npm install --save-dev prettier```

         3. workspace/.prettierrc
          
            : setting => "semi" : false , (세미콜론 사용하지 않음 여부)
                      => "singleQuote " : true (작은 따옴표 or 큰 따옴표) 
          
         4. workspace/.vscode/settings.json

             ```
             {
                "[javascript]": {
                  "editor.formatOnSave": true,
                  "editor.defaultFormatter": "esbenp.prettier-vscode"
                }
             }
             ```
        
      : Linting :ESLint
      
         1.  ``` npm install --save-dev eslint ```

         2. workspace/ .eslintrc.js

                ```module.exports={}``` 
                => {}안에 룰들을 기재해야함
               
            하지만, 기재할 필요없이 best plugin 중 하나의 config를 사용
               
                ``` npm install --save-dev eslint-config-airbnb-base eslint-plugin-import ```
               
                ``` 
                module.exports = {
                     extends : ['airbnb-base', 'prettier'],
                }
                   
                ```
                
         => eslint 와 prettier가 겹치는 현상이 발생함.
      
      
               ```npm install --save-dev eslint-config-prettier```
      
      
