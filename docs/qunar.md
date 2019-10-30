# 去哪儿 NodeJs版API  
去哪儿网数据接口

# 工作原理
数据库：MongoDB
数据源：nodejs爬，调用官网接口


# 注意：
该项目开源，已部署在服务器上，可以直接调用接口。

线上地址：http://zyuanyuan.com/qunarApi
在后面追加对应的接口地址即可使用

例如：[http://zyuanyuan.com/qunarApi/cities](http://zyuanyuan.com/qunarApi/cities)

感兴趣的同学可以下载源码,自己部署。


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
 
## 2. 获取指定城市首页数据（cityid）
说明：调用此接口，传入指定城市id值`cityid`  就可以获取指定城市的首页数据

****必选参数****：`cityid`:城市id值， 可以在`1`接口处查看

 **接口地址**：`/cityDetail/cityid/:cityid`
 
 **调用例子**：`/cityDetail/cityid/5daeff860901966168310e1c`
 
## 3. 获取指定城市首页数据(cityName)
说明：调用此接口，传入指定城市名`cityName`  就可以获取指定城市首页数据

****必选参数****：`cityName`:城市名称， 可以在`1`接口处查看
 
 **接口地址**：`/cityDetail/cityname/:cityName`
 
 **调用例子**：`/cityDetail/cityname/北京`
 
 
## 4. 获取指定城市的本周热门榜单(cityid)
说明：调用此接口，传入指定城市id值`cityid`,可以获取指定城市的本周热门榜单

****必选参数****：`cityid`:城市id值， 可以在`1`接口处查看
 
 **接口地址**：`/hostList/cityid/:cityid`
 
 **调用例子**：`/hostList/cityid/5daeff860901966168310e1c`
 
 
## 5. 获取指定城市的周热门榜单(cityName)
说明：调用此接口，传入指定城市名`cityName`,可以获取指定城市的周热门榜单

****必选参数****：`cityName`:城市名称， 可以在`1`接口处查看
 
 **接口地址**：`/hostList/cityname/:cityName`
 
 **调用例子**：`/hostList/cityname/北京`
 
 
 ## 6.  获取指定景点详情数据
说明：调用此接口，传入景点id值`id`,可以获取指定景点详情数据

****必选参数****：`id`:景点id值
 
 **接口地址**：`/addrDetail/id/:id`
 
 **调用例子**：`/addrDetail/id/989946426`
 
 
 ## 7. 获取指定地区的评论数据
说明：调用此接口，传入指定地区的id值等参数，可以获取相应评论数据
 
****必选参数****：`sightId`:景点id值
****可选参数****：`pageNum`:评论页数，默认为1。参数1和0获取的数据相同。
****可选参数****：`pageSize`:评论条数，默认为10。这个就默认，不要传参。因为不管传多少，官网返回的数据都为10条，传10以下的数值，则请求不到数据。
****可选参数****：`tagType`:评论标签，默认为0。表示全部。具体选项可在获取的数据的`tagList`数组里查看。
 
 **接口地址**：`/comments`
 
 **调用例子**：`/comments?sightId=2267`  `/comments?sightId=2267&pageNum=2&tagType=41`
 
 
 
 
 
 