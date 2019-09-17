#vue路由提供了三种监听路由变化的方式

第一种 全局监听

​	所有的路由变化，都会监听到

​	在路由实例化对象上，通过beforeEach， afterEach等方法监听路由的改变

​		参数是回调函数

​			回调函数的参数

​					第一个表示当前路由对象

​					第二个参数表示上一个路由对象

​					如果是beforeEach会出现第三个参数，类似express路由中间件的第三个参数，next方法，是否继续执行，该					方法必须执行。

第二种 局部监听

​		只针对某个组件监听路由的变化

​		我们在组件实例化对象上，通过beforeRouteEnter, beforeRouteLeave, beforeRouteUpdate等方法可以监听路由的变		化。

​				第一个参数表示当前的路由对象

​				第二个参数表示上一个路由对象

​				第三个参数表示执行进入路由的方法，必须要执行

第三种 watch监听

​			我们可以通过组件实例化对象的watch监听路由数据的变化

​			可以监听$route属性的变化，来判断路由

​				第一个参数表示当前的路由对象

​				第二个参数表示上一个路由对象

```bash
1	// 局部监听
2	beforeRouteEnter(route, oldRoute, next) {
3		console.log(arguments)
4		// 必须执行next方法
5		next();
6	}

7	// 监听路由的变化
8	watch: {
9		// 路由数据的变化
10		$route() {
11			// console.log(111, arguments)
12			// 更新数据
13			this.updateData();
14		}
15	}
16	// 监听路由变化
17	router.afterEach((...arg) => console.log(arg))
18	// 改变之前
19	router.beforeEach((route, oldRoute, next) => {
20		console.log(route, oldRoute)
21		// 必须要执行
22		next();23	})

```













