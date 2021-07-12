#### 解决Vetur can`t find  'tsconfig.json' or  'jsconfig.json'

------

1. 在项目根目录加个jsconfig.json

2. 内容如下

   ```json
   { 
    "include": [ 
    "src/**/*" 
    ], 
    "compilerOptions": { 
        "baseUrl": ".", 
        "paths": { 
        "@/*": [ // 解决vscode不识别@ 
        "src/*" 
        ] 
        } 
     } 
   } 
   ```

   