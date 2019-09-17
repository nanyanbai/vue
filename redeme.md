vue-cli 实现思路

vue init webpack my-pp  ---webpack 模板 ---模板引 --- 本地项目

- 项目模板放在github上

- 用户通过命名交互的方式下载不同的模板

- 经过模板引jie渲染定制项目模板

- 模板变动，只需要更新模板即可，不需要用户更新脚手架

  

------

#### 命令行工具参数设计

```
vue -h 或者 --help   查看使用帮助
vue -v 或者 --version 查看工具的版本号
vue list  列出所有可用模板
vue  init <template-name> <project-name> 基于指定的模板进行项目初始化
```

查看可用的npm源

```
nrm ls
```

如何看npm是最新的版本

```
$ npm show npm
```





**vue-cli的前期准备**

**（一）vue-cli的安装**

推荐环境：

​	node.js 8.10以上

​	npm最新版本

 卸载旧版本（1.x或2.x）

​	npm   uninstall  vue-cli  -g

安装3.X版本

​	npm  install  -g  @vue/cli

​    vue  --version (或vue -V)

​	这就是安装vue 3.x的最新版本

![1558056077403](C:\Users\yhfz11\Desktop\学习笔记\vue\1558056077403.png)

​		

**（二） 用vue-cli创建项目**

​	建立新项目

```
$ vue create vue-demo
```

![1558057054565](C:\Users\yhfz11\Desktop\学习笔记\vue\1558057054565.png)

**（三）启动新项目**

​		cd  vue-demo

​		npm run serve



**注意**

1.修改默认端口号是在config目录下面的index.js文件中找到port：8080 可以自行修改它的端口号的。

2.在启动项目的时候让自动在浏览器中打开也是在config目录下的index.js中找到autoOpenBrowser 改为true即可



**操作：**

```
npm  install -g vue-cli
vue init webpack gshope(也就是项目名称)
cd gshope
npm install
npm run lint
npm run dev
```



**项目结构分析**

|-- build ：webpack相关的配置文件夹（基本不需要修改）

|-- config:  webpack相关的配置文件夹（基本不需要去修改）

​			 |-- index.js ： 指定的后台服务器的端口号和静态资源夹

|-- node_modules 

|-- src : 源码文件夹

​	     |-- main.js: 应用入口js

 |-- static :静态资源文件夹

 |--  .babelrc ： babel的配置文件

 |--   .editorconfig： 通过编辑器的编码/格式进行一定的配置

 |--  .eslintignore : eslint 检查忽略的配置

|--  .eslintrc.js  eslint的检查配置

|-- .gitignore   git版本忽略的配置

|-- index.html ：主页面文件

|-- package.json ：应用包配置文件

|-- README.md： 应用描述说明的readme文件



**打包：**

```
npm run build
```

发布静态服务器工具包

```
npm install -g serve
serve dist
```

访问： http://localhost:5000



**项目源码目录设计**

![1558937387178](C:\Users\yhfz11\Desktop\学习笔记\vue\1558937387178.png)

安装stylus依赖包

```
npm install stylus stylus-loader  --save-dev
```

编写样式

<style lang="stylus" rel="stylusheet/stylus"></style>

