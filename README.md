# 面试题积累
  
    1、多人合作开发项目时如何组织代码？

  > 在实际项目中，如果单纯的按model、view、controllers、template 等文件夹进行分类，等项目做大或者文件复杂后，就会出现混乱。因为不清楚引用关系。
> 在项目中，我们经常会修改或者维护单一的页面或者某个功能模块。如本文所说按功能模块或者页面进行文件组织确实是个不错的方法。
> 同时，也可以两者结合起来：先按项目功能分文件夹，里面再按MVC的架构细分文件夹。
> 每个项目都有一些common之类的功能模块，如果一个功能或者函数，有超过2个以上的页面使用，就将它放于common文件夹。
 
    2、js 如何避免全局污染
```
为何要尽量避免全局变量污染呢？
全局变量减少了js的灵活性，增加了耦合性。
若一个项目是由多人合作完成，全局变量容易造成变量名冲突。
根据垃圾回收机制，一个变量的生命周期的结束要等到不再使用该变量，而全局变量则要到关闭浏览器页面才会被回收，所以及其占用内存。
```
解决方法：
1.使用一个全局变量作为容器，将属性跟方法都添加到该对象上
```
var contain = {};
var contain.fn = function() {
// ....
}
```
2.使用自执行函数
```
(function() {
// ...
})()
```



    3、 闭包的作用
> 闭包就是由函数创造的一个词法作用域，里面创建的变量被引用后，可以在这个词法环境之外自由使用。闭包通常用来创建内部变量，使得这些变量不能被外部随意修改，同时又可以通过指定的函数接口来操作
> http://blog.csdn.net/sunlylorn/article/details/6534610

4、 h5新标签

> http://www.jianshu.com/p/b4393e798737

5、 ajax同步和异步的处理

> AJAX中根据async的值不同分为同步（async = false）和异步（async = true）两种执行方式
> $.ajax()的async参数总是设置成true，这标志着在请求开始后，其他代码依然能够执行

6、 了解nodejs吗？
7、 设计一个可复用的button组件

8、 react 无状态组件
    无状态组件就剩了一个 render 方法，因此也就没有没法实现组件的生命周期方法，例如 componentDidMount, componentWillUnmount 等。
- 优点

相比于 class 创建组件

- 语法更简洁
占内存更小（class 有 props context _context 等诸多属性），首次 render 的性能更好
. 可以写成无副作用的纯函数
可拓展性更强（函数的 compose，currying 等组合方式，比 class 的 extend/inherit 更灵活）
- 缺点

- 无生命周期函数

一个组件就是一个函数，函数应该是谈不上生命周期的，但是组件却是有生命周期，stateless functions 没有生命周期。当然了，我们其实可以使用 高阶组件 去实现生命周期

- 没有 this

在 stateless functions 中，this 是 undefined，所以是不能使用 this 变量。不过换个角度思考，this 是在运行时随时可以被修改或重新赋值，跟外界环境有着密切的联系，正是不使用this才会让组件变得更纯。
例子：
改写前：
```
class ReactFormLabel extends React.Component {
    constructor() {
        super();
    }
    render() {
        return(
            <label htmlFor={this.props.htmlFor}>{this.props.title}</label>
        )
    }
}
```
改写后： 
```
const ReactFormLabel = (props) => 
    <label htmlFor={props.htmlFor}>{props.title}</label>;
```
9、 js 取并集
10、 纯css实现三角形
11、 react 生命周期， componentWillMount的意思， 哪个生命周期调用ajax
12、 ios微信端滑动缓慢
13、 手机端设置不能放大
14、 localstroge存储和取值
15、 canvas绘制长方形
16、 react classComponent 和 function componenet的区别
17、 echarts环形双层图
18、 
