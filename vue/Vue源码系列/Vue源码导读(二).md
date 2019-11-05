# Vue源码导读(二)--搭建调试环境



### 安装依赖

下载好Vue源码后使用`npm install`安装依赖

vue是基于rollup构建的 , 所以如果没有安装rollup , 要先安装rollup

npm安装 : `npm i -g rollup`



### 生成SourceMap

修改`package.json`中dev脚本 , 加上`--sourcemap` 

```json
"scripts": {
  "dev": "rollup -w -c scripts/config.js --sourcemap --environment TARGET:web-full-dev"
  . . .
}
```

此命令用于运行时生成sourcemap映射文件 , 方便我们进行调试

运行`npm run dev` , dist目录下如果生成了`vue.js.map` 就ok了



**注 : **如果你是windows系统 , 在执行`npm run dev`时可能会报错如下

```js
[!](plugin Rollup Core) Error: Could not load e:/work-isboyjc/isboyjc/vue/src/core/config (imported by e:\work-isboyjc\isboyjc\vue\src\platforms\web\entry-runtime-with-compiler.js): ENOENT: no such file or directory, open 'e:\work-isboyjc\isboyjc\vue\src\core\config'
```

1. 确保你的vue源码路径无中文
2.  `roullp-plugin-alias` 插件对于windows的盘符解析忽略了小写的情况

修改方法 : 

找到`node_modules/rollup-plugin-alias/dist/rollup-plugin-alias.js`文件在大概13行的位置修改如下

```js
const VOLUME = /^([A-Z]:)/i; // 加上i , 忽略大小写
const IS_WINDOWS = os.platform() === 'win32';
```

重新运行`npm run dev` , 问题解决!



> 此处参考 : [vue.js 2.0 alpha error on start on windows 10 x64](https://github.com/vuejs/vue/issues/2771#issuecomment-446090852)





### 创建调试文件

创建调试文件`index.html`如下

```html

```











