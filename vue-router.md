[Vue Router](https://router.vuejs.org/zh/)

vue路由配置

1.安装

​	npm install vue-router  --save  / cnpm  install  vue-router  --save

2.引入并Vue.use(VueRouter)     在main.js

​      import  VueRouter  from 'vue-router'

​     Vue.use(VueRouter)

3.配置路由

1> 创建组件，引入组件

2> 定义路由 （建议复制）

```js
// 每个路由应该映射一个组件。 其中"component" 可以是
// 通过 Vue.extend() 创建的组件构造器，
// 或者，只是一个组件配置对象。
// 我们晚点再讨论嵌套路由。
```

```js
const routes = [
  { path: '/foo', component: Foo },
  { path: '/bar', component: Bar },
  { path: '*', redirect: '/home' }  //默认跳转路由
]
```

3>实例化VueRouter

```js
const router = new VueRouter({
  routes // (缩写) 相当于 routes: routes
})
```

4>挂载

```js
new Vue({
  el: '#app',
  routes,
  render: h => h(App)
})
```

5> 根组件模板里面放<router-view></router-view>  放在App.vue里面

**不同路由传值：动态路由**

1.配置动态路由

```js
routes: [
  //动态路径参数，以冒号开头
    { path: '/user/:id', component: User }
]
```

2.在对应的页面

this.$route.params

**Vue中路由嵌套**

1>配置路由

```js
{
  path: '/user',
  component: User,
    children : [
      { path: 'adduser', component: Adduser },
      { path: 'userlist', component: UserList }
    ]
}
```

2>父路由里面配置子路由显示的地方

​	<router-view  ></router-view> 

**mintUI的使用**

1.找官网

2.安装 npm install  minit-ui  -S           -S表示 --save

3.引入mint UI的css和插件

​	import  Mint  from 'mint-ui';

​	Vue.use(Mint);

​	import  'mint-ui'/lib/style.css'

4.直接使用

​	







