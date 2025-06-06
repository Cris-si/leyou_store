

        			乐优商城项目总结

##  1.个人心得总结

​	这个项目我跟着做，包括独立完善一些增删改查的业务大概25天左右。也只是完成了商城部分主体业务:用户搜索商品，加入购物车，注册登录，下单支付，和后台商品管理，品牌管理。之前做过一个ssm的项目，对软件系统开发有一定的感受。做完这个项目，对软件系统开发有了一个更加具体的认知，同时也学到了很多新的技术，收获颇丰！



## 2.项目架构图

  首先可以看一下项目架构图

​	前端主要使用了vue及其相关的框架来构建界面，通过nodejs来部署到服务器，请求的发送通过nginx进行转发，全部请求都要经过网关进行处理，在网关处需要进行权限的鉴定和处理，确定有对应权限后才可以转发访问微服务集群。微服务集群有很多，不同权限的用户可以访问不同的微服务。所有的请求都是由网关进行转发的，使用了相应的框架做了负载均衡，并有熔断处理。微服务与微服务之间的通知调用使用了消息队列框架来实现。最终使用了redis,mysql等来存储不同类型的数据。使用了elasticsearch来当索引库，作为搜索服务的数据库。

![52570375903](/readmeImg/1525703759035.png)





## 3.技术选型

### 3.1 前端技术：

- 基础的HTML、CSS、JavaScript（基于ES6标准）
- JQuery
- Vue.js 2.0以及基于Vue的框架：Vuetify
- 前端构建工具：WebPack 
- 前端安装包工具：NPM
- Vue脚手架：Vue-cli
- Vue路由：vue-router
- ajax框架：axios 
- 基于Vue的富文本框架：quill-editor 



### 3.2 后端技术：

- 基础的SpringMVC、Spring 5.x和MyBatis3
- Spring Boot 
- Spring Cloud 
- Redis  
- RabbitMQ
- Elasticsearch
- nginx
- FastDFS
- MyCat
- Thymeleaf
- mysql 5.6

## 4.完成后的部分页面展示

### 4.1后台管理界面

![台商品管理页](/readmeImg/后台商品管理页面.png)

### 4.2 后台添加商品界面

![增商品页](/readmeImg/新增商品页面.png)



### 4.3 注册登录页面

![录页](/readmeImg/登录页面.png)

![册页](/readmeImg/注册页面.png)



### 4.4 分类搜索界面

![类搜索界面](/readmeImg/分类搜索界面1.png)

![搜索界面](/readmeImg/搜索界面2.png)







### 4.5 商品详情界面

![商品详情](/readmeImg/商品详情页.png)





### 4.6 购物车界面

![购物车页](/readmeImg/购物车页面.png)



### 4.7 结算界面

![算页](/readmeImg/结算页面.png)



### 4.8 微信支付界面

![付界](/readmeImg/支付界面.png)





## 5.如何启动项目

### 5.1 虚拟机相关配置

​	这里把多东西安装在了虚拟机中，如FastDfs,redis,RabbitMQ,Elasticsearch，虚拟机环境是CentOS7,首先你要确保安装这些东西，安装elasticsearch时可能会遇到较多的问题。

### 5.2 文件说明

​	leyou-manage-web是后台界面，leyou-protal是前台界面，leyou文件夹是后台代码

### 5.3启动顺序及相关命令

前台商城展示页面部署：live-server --port=XXX 即可热部署在XXX端口

后台管理页面部署:

npm init -y  # 进行项目初始化

npm install vue --save # 安装

vuenpm install # 安装依赖

npm run dev # 启动项目

后台启动：首先修改各个微服务模块的配置文件 ，ip地址和端口号数据库等等配置写你的。接着找到引导类启动各个模块的微服务。虚拟机里面的相关服务也要启动，就可以正常运行了。





