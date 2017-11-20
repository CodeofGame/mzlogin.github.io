### 使用原生ajax发送请求

> jaax

##### XMLHttpRequest对象方法一览

- XMLHttpRequest.open(method, url[, async, username, password])

  功能:设置请求的类型，请求的地址，是否异步

  method：请求类型GET,POST,PUT DELETE

  url：目标url地址

  async：是够异步,值为true时，异步调用，值为false时，同步调用

  username：可选参数

  password：可选参数

- XMLHttpRequest.send([string])

  功能:将请求发送到服务器

  string:

- onreadystatechange发送请求之后执行的函数(回调函数)

  ```javascript
  var xhr=new XMLHttpRequest();
  var url="http://localhost:1589/wkinfo/Test";
  xhr.open("Get",url,true);
  xhr.onreadystatechange=function(){
    
  }
  ```

  ​

跨域的严格一点的定义是：只要 协议，域名，端口有任何一个的不同，就被当作是跨域