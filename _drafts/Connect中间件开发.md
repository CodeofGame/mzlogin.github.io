# Connect中间件开发

> Connect 是一个框架，中间件的模块化组件。简单点说Connect中间件其实就是一个函数，拦截http服务器的请求和响应，待这个中间件处理完毕之后，我们可以选择响应客户端，也可以吧请求和响应传递飞下一个中间件。Connect 相较 Express 更加底层，Express 添加了更多的高层糖衣，方便开发人员调用。





中间件的顺序很重要

#### 挂载中间件和服务器

## 模板引擎

### jade模板引擎

```shell
npm all -g jade
```

全局安装jade，必须全局安装，否则无法使用jade命令

新建文件index.jade

```jade
//index.jade
doctype html
html
	head
		title 学习Jade模板引擎
	body
		h1 侯晗彬  
```

上面是一个最简单的jade模板，使用命令

```shell
jade index.jade       --生成一个压缩的html，名为index.html
jade -P index.jade    --生成不压缩的html这里的P是大写的P
```

如果频繁的修改文件，修改再输命令，那么开发效率肯定特别低，所我们可以使用一个参数监视文件，如果jade文件改变，立马编译出新的html

```shell
jade -P -w index.html --实时编译html文件
```

##### jade语法

- 注释

  ```jade
  !.单行注释
  // <h1>单行注释</h1>    --注释后的代码也会被编译到html中
  2.非缓冲注释
  //- <h1>非缓冲注释</h1>  --注释的代码不会出现在html中
  3.d块注释
  ```

- 在jade中声明变量


```shell
//声明变量
- var title = 'jade'
//使用变量
h2 #{title}        =>            <h2>jade</h2>
//jade中的变量也带一些方法,例如让英文大写
h2 #{title.toUpperCase()}    =>       <h2>JADE</h2>
```

但是有时我们并不会直接在jade页面中定义变量，这个变量有可能是通过接口返回的json数据

怎么让jade页面接收变量

- 通过命令行

```shell
jade -P -w index.jade --obj '{"title":"jade"}'
```

- 通过json文件中读取（在变量特别的多的时候使用）

```json
//var.json
{
  "title":"jade"
}
```

再通过命令行

```shell
jade -P -w index.jade -O var.json
```

#### jade中的转义

如果变量中包含包含特殊符号，例如>,<,这种符号,

```shell
- var x = '<script>alert(1)</script>'
h2 #{x}   ==>  <h2>&lt;script&gt;alert(1)&lt;/script&gt;</h2>
h2 !{x}   ==>  <h2><script>alert(1)</script></h2>
//简写方式
h2=x    ==>  <h2>&lt;script&gt;alert(1)&lt;/script&gt;</h2>
h2!=x   ==>  <h2><script>alert(1)</script></h2>
//有些情况下就要输出#和{}
```

