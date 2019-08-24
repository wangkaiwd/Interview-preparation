## 复习计划
> 将除`css`和`html`之外的所有题目都自己总结答案，然后进行简单的复习

## `Vue`
### 生命周期的详细流程
首先看一下我们创建`vue`实例代码：
```js
const vm = new Vue({
  render: h => h(App)
}).$mount('#app');
```
* 通过`new Vue`传入配置参数来构建`Vue`实例
* 初始化事件和生命周期
* `beforeCreate`: 实例初始化后,`this`指向创建的实例，不能访问`data`,`copmuted`,`methods`等属性
* `initState`
* `created`: 完成了一些属性的初始化：`data`,`computed`,`methods`,所以这时可以使用`this.data`,`this.props`等来访问这些属性和方法。但是`DOM`并为挂载，所以不能访问到`$el`和`$ref` 属性
* 挂载虚拟`DOM`: 之后`Vue`会判断传入的配置项中是否有`$el`选项，如果没有的话会通过`vm.$mount`(实例的`$mount`方法)将`Vue`挂载到传入的根实例中。
* 挂载根组件： 之后`vue`会判断传入的配置项中是否有`template`选项，有的话将`template`作为根组件渲染，否则会将`el`对应的节点的`outerHTML`得到的字符串作为根组件渲染。
* `beforeMount`: 不能访问`$el`
* 挂载`DOM`: 创建`vm.$el`并替换之前虚拟的`el`
* `mounted`: 可以操作`DOM`，即可以访问`$el`和`$ref`属性
* `beforeUpdate`: 当`data`改变的时候会触发该钩子函数，此时虚拟`DOM`还没有更新完毕
* `updated`: 当虚拟`DOM`重新渲染和打补丁(`virtual dom re-render and patch`)结束后调用，可以在`DOM`更新后进行一些操作，最好加条件判断，否则会造成死循环
* `beforeDestroy`: 当组件被卸载的时候(比如切换组件或手动调用`vm.$destroyed`)触发，在该生命周期中可以访问`this`实例，可以取消事件订阅或定时器
* `destroyed`: 组件卸载之后调用
### 详细的`popover`组件的一个实现思路
### 双向数据绑定的原理

### 原生
* `axios`源码部分解读

## `React`

### `React`生命周期

### `setState`到底是异步还是同步

### `React`组件通信

### `Redux`工作流程

### `redux-thunk`解读