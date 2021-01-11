 
 - script 中 会的命令会默认补全 `./node_modules/.bin/`  eslint --init

 使用 npm  script 中 的命令 可以用来 运行 scirpt 中脚本的代码
 这样一来就可以检查 代码规范 和  css规范 
 npm t/ test  
 
 ```json
 "test": "npm run lint:js & npm run lint:css & wait" // 并行
 "test": "npm run lint:js && npm run lint:css" // 串行
 ```

     "test": "npm run lint:js & npm run lint:css & wait",

 当然也有简单的方法 

 ```patch
 + npm install npm-run-all -D
```
```patch
- "test": "npm-ru-all lint: *",
+ "test": "npm-run-all --parallel lint: *"
```


以上功能如果用了webpack 都能实现，比较方便， 当然在做node 项目的时候可以用着.
主要是如果你的项目如果没有用到 webpack

给 json 文件添加 注释
因为是json 文件 所以没有办法直接使用 // ， 但是可以把 // 作为一个 key , value 为其注释内容 

 有时候我们需要知道 npm 执行脚本的时候发生了什么 我们需要打印日志

 ```json 
 npm t -s // 只会打印出错误，其他不会打印，如果没有错误就不打印
 npm t -d   
 npm t --verbose
 ```
 