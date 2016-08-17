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
       var koa = require('koa');
       var fs = require('fs');
       var app = koa();
       
       app.use(function *(){
           //this.response;
           var html = fs.readFileSync('hello.html');
           this.set({
               "Content-Type": "text/html"
           });
           this.body = html;
       });
       
       app.listen(3000);
       
/* wangxiaobo 16/8/17 */
