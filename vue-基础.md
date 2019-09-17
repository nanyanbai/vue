# 介绍

**Vue.js  介绍描述**

1）渐进式JavaScript 框架

2) 作者： 尤雨溪

3）作用： 动态构建用户界面

**Vue 的特点**

1）遵循MVVM模式

2）编码简洁，体积小，运行效率高，适合移动端/PC端开发

3）它本身只关注UI, 可以轻松引入vue插件或其它第三库开发项目

**Vue 扩展插件**

1）vue-cli : vue脚手架

2）vue-resource(axios):ajax请求

3）vue-router: 路由

4）vuex:状态管理

5）vue-lazyload ：图片懒加载

6）vue-scroller：页面滑动相关

7）mint-ui: 基于vue的UI组件库（移动端）

8) element-ui：基于vue的UI组件库（PC端）

**Vue的基本使用**

1）.创建Vue实例

2）.el: 指定根element（选择器）

3）.data :初始化数据（页面可以访问）

4）.显示数据：{{xxxx}}

**Vue:export  default 中的name属性到底有啥作用呢？**

#name

​	类型：string

​	限制：只有作为组件选项时起作用

​	**组件自身的递归调用，就是在当前组件中，调用组件自己**

**单独的一个vue文件如何让它跑起来：**

```
npm  intall  -g @vue/cli-service-global
```



Vue父组件给子组件传值 ，Vue父组件给子组件传方法，Vue父组件把整个实例传给子组件

Vue父组件给子组件传值：

​	1）父组件调用子组件的时候，绑定动态属性

​	2） 在子组件里面我们接受父组件传过来的数据



## 路由（router）

```
routes: [
	{
		path:'/',
		name:'',
		component:
	}
]
```

单词解释：

routes ---> 路线

注意：

path是路由的路径

name是路由的名字

component是要加载的组件

要使用组件得把它导入进来

```
import  组件名  from   '组件在哪个目录下'
```

```
import  HelloWorld  from  '@/components/HelloWorld'
```

注意： 上面@代表的是src  是在webpack.base.conf.js里面的一个配置。	


如果不使用路由的话，如何使用组件呢 ？


1.	先创建组件
2.	在要展示组件的地方把组件引入进来    
3.	然后要注册组件   components: { HelloWorld}
4.	最后把这个组件名放到页面中


组件传参

父-子 传参

在子组件中用props 接受父传过来的参数





