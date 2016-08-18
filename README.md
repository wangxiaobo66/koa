# koa
nodeJs环境下koa框架初试

##一、安装node.js 
       很简单没啥好写的
###Koa框架搭建：
       1、npm install koa到指定项目
##二、环境测试：
    因为nodeJs 不仅可以作为web的后端，而且它甚至就是一个后端服务器环境，你可以通过脚本来创建一个后端服务。
    在项目根目录下创建一个hello.js文件。
    var http = require("http");
    http.createServer(function(request,response)
    {
        response.writeHead(200,{"Content-Type":"text/plain"});
        response.write("Hello World");
        response.end();
    }).listen(8888);
    保存并运行它，node hello.js。

/* Created by wangxiaobo on 16/8/17 */

##与koa相结合
###fs(File System)
关于文件操作，那么这边主要的就是fs这个模块。对于node中fs模块提供的API很多，但是其所有的方法均有同步和异步的形式。对于读取文件内容来说，最需要注意的一点就是异步与同步之间控制执行流程的问题。
下面用的是fs.readFileSync(filename, [options])，一个同步执行读取本地文件的过程：

       var koa = require('koa');
       var fs = require('fs');
       var app = koa();
       
       app.use(function *(){
           var html = fs.readFileSync('hello.html');
           this.set({
               "Content-Type": "text/html"
           });
           this.body = html;
       });
       
       app.listen(3000);
       
/* wangxiaobo 16/8/17 */

##koa中间件学习
###koa-convert
今天卡壳。。明天再写

/* wangxiaobo 16/8/18*/
