# 去哪儿 NodeJs版API  
本项目通过采集去哪儿网的部分数据，制作模拟了一部分的api接口。
提供给大家测试学习！

# 适用者
想写个小项目练手又苦于没有完整的数据源的同学们。

# 工作原理
nodjs爬取数据，存入MongoDB数据库，通过路由使用接口。   

# 注意：
该项目开源，已部署在服务上，可以直接调用接口使用。
感兴趣的同学可以下载源码，自己研究研究。

# 安装 
[GitHub项目地址](https://github.com/zoyoy1203/qunarApi)
```
$ git clone git@github.com:zoyoy1203/qunarApi.git

$ npm install
```
# 运行
```
$ node server/index.js
```
# 接口文档

## 1. 获取所有城市数据
说明：调用此接口，可以获取所有城市数据

 ****接口地址****：`/cities`
 
 ****调用例子****：`/cities`
 
## 2. 获取指定城市首页数据
说明：调用此接口，传入指定城市id值`cityid`  就可以获取指定城市的首页数据

****必选参数****：`cityid`:城市id值， 可以在`1`接口处查看

 **接口地址**：`/cityDetail/cityid/:cityid`
 
 **调用例子**：`/cityDetail/cityid/5daeff860901966168310e1c`
 
## 3. 获取指定城市首页数据
说明：调用此接口，传入指定城市名`cityName`  就可以获取指定城市首页数据


****必选参数****：`cityName`:城市名称， 可以在`1`接口处查看
 
 **接口地址**：`/cityDetail/cityname/:cityName`
 
 **调用例子**：`/cityDetail/cityname/北京`
 
 
## 4. 获取指定城市的本周热门榜单
说明：调用此接口，传入指定城市id值`cityid`,可以获取指定城市的本周热门榜单

****必选参数****：`cityid`:城市id值， 可以在`1`接口处查看
 
 **接口地址**：`/hostList/cityid/:cityid`
 
 **调用例子**：`/hostList/cityid/5daeff860901966168310e1c`
 
 
## 5. 获取指定城市的周热门榜单
说明：调用此接口，传入指定城市名`cityName`,可以获取指定城市的周热门榜单

****必选参数****：`cityName`:城市名称， 可以在`1`接口处查看
 
 **接口地址**：`/hostList/cityname/:cityName`
 
 **调用例子**：`/hostList/cityname/北京`
 
 
 ## 6.  获取指定景点详情数据
说明：调用此接口，传入景点id值`id`,可以获取指定景点详情数据

****必选参数****：`id`:景点id值
 
 **接口地址**：`/addrDetail/id/:id`
 
 **调用例子**：`/addrDetail/id/989946426`
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 ## 待更新...