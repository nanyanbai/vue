**Vue组件化思想**

组件化是Vue.js中的重要思想

它提供了一种抽象，让我们可以开发出一个个独立可复用的小组件来构造我们的应用

任何的应用都会被抽象成一颗组件树

**注册组件的基本步骤**

1.创建组件构造器

2.注册组件

3.使用组件

![ç»ä»¶åå»º](https://segmentfault.com/img/bV4jY4?w=388&h=639)

Vue组件的最基本使用：

```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title>title</title>
	</head>
	<body>
		
		<div id="app">
			<!--3.使用组件-->
			<my-cpn></my-cpn>
		</div>
		<script src="js/vue.js"></script>
		<script>
			//1.创建组件的构造器
			const cpnC = Vue.extend({
				template:`
					<div>
						<h2>我是标题</h2>
						<p>我是内容哈哈</p>
						<p>我是内容呵呵</p>
					</div>
				`
			})
			//2.注册组件
			Vue.component('my-cpn',cpnC);
			
			const  app = new Vue({
				el:'#app',
				data:{
					
				}
			})
		</script>
	</body>
</html>

```

**全局组件和局部组件**

**1.全局的组件**

（1）我们使用 **Vue.component(tagName, options)** 可以注册一个**全局的组件**，也就是说它们在注册之后可以用在任何新创建的 Vue 根实例 (new Vue) 的模板中。

```vue
Vue.component('my-button', { 
    template: `<button>点击我</button>` 
})
```

（2）注册组件：	

```html
Vue.component('my-button', myButton) 
```

（3）组件注册之后，便可以作为**自定义元素** <my-button />，在一个实例的模板中使用。【注意】**在初始化根实例之前注册组件**。

```
<div id="app"> 
    <my-button /> 
</div>
```

**2.局部组件**

（1）通过某个Vue实例/组件的实例选项 **components** 注册，使用该选项注册的组件被称为局部注册。

```vue
let myButton = Vue.extend({ 
    template: `<button>点击我</button>` 
})

let app = new Vue({ 
    el: '#app',
    components: {
        'my-button':myButton
    }
}) 
```

```vue
<div id="app"> 
    <my-button /> 
</div>
```

（2）得到的效果和注册全局组件是一样的。不同的是，如果你在**另一个**Vue实例中调用注册的局部组件，该组件**不会生效**。比如在app2这个实例中调用app中注册的组件my-button，就不会生效。