# 豆果美食NodeJs版API

# 灵感来自
以前刚开始学习前端，想写个小项目练练手，每次找数据接口都要花好大的力气。甚至能否找到数据接口决定了我的项目是否能够继续下去。
很多平台的数据免费试用请求一定数量后，就要求付费。
无奈学生党，花费不起。自己写后端，对于那个时候刚起步前端的我，是不太切合实际的，而且还要花费大量的精力和时间去学习后端，爬虫收集数据等。
这跟我想写个复杂的小项目，提升前端技术的初衷背道而驰。

# 适用者
初入前端，想要写个小项目练手的同学们

# 工作原理
伪造请求头，调用官方API   

# 注意：
该项目开源，已部署在服务器上，可以直接调用接口。

线上地址：http://zyuanyuan.com/foodsApi
在后面追加对应的接口地址即可使用

例如：[http://zyuanyuan.com/foodsApi/home](http://zyuanyuan.com/foodsApi/home)

# 安装 
[GitHub项目地址](https://github.com/zoyoy1203/FoodsApi)
```
$ git clone git@github.com:zoyoy1203/FoodsApi.git

$ npm install
```
# 运行
```
$ node app.js
```
# 接口文档

## 获取首页数据
说明：调用此接口，可以获取豆果美食首页数据

 ****接口地址****：`/home`
 
 ****调用例子****：`/home`
 
## 获取菜谱分类
说明：调用此接口，可以获取菜谱分类数据

 **接口地址**：`/recipe/catalogs`
 
 **调用例子**：`/recipe/catalogs`
 
## 获取相关菜谱分类里的菜谱列表
说明：调用此接口，传入分类关键字`keyword`，可以获取相应菜谱列表

 ****必选参数****：`keyword`:菜谱关键字
 
 **接口地址**：`/recipe/list`
 
 **调用例子**：`/recipe/list?keyword=土豆`
 
## 获取菜谱详细内容（包含制作过程，评论等）
说明：调用此接口，传入菜谱id,可以获取菜谱详细内容

 ****必选参数****：`id`:菜谱id
 
 **接口地址**：`/recipe/detail`
 
 **调用例子**：`/recipe/detail?id=839234`
 
## 获取商城首页数据
说明：调用此接口，可以获取商城首页数据（包含分类列表，每日秒杀，好物推荐，近七日爆款等）
 
 **接口地址**：`/shop`
 
 **调用例子**：`/shop`
 
## 获取商城分类里的商品列表
说明：调用此接口，传入商城分类`id`,可以获取商城分类里的商品列表

 **必选参数**：`id`:商城类别id
 
 **可选参数**：`or`:默认0：  综合0 销量1 价格升序2 价格降序3 新品4
 
 **接口地址**：`/shop/list`
 
 **调用例子**： `/shop/list?id=10`    `/shop/list?id=10&or=3`   
 
## 获取商城商品详情
说明： 调用此接口，传入商品`id`，可以获取商城商品详情

 **必选参数**：`id`:商城商品id
 
 **接口地址**：`/shop/detail`
 
 **调用例子**： `/shop/detail?id=28225`  
 
## 获取课程首页 ，后续课程
说明：调用方式有2种：传参和不传参
1. 不传参： 默认`offset=0,limit=20`  调用此接口，获取课堂首页数据  (包块今日秒杀，热门推荐，新课上线，电子书，全部课程的栏目数据20条等)
1. 传参：`offset`:偏移数量，`limit`:返回数量  （不传参默认返回首页全部课程栏目的20条数据，当首页滚动到底部时，若需要加载显示offset(20)条开始的后limit条课程数据，需传参请求）
 
 **接口地址**：`/course`

 **调用例子**： `/course`   `/course?offset=20&limit=1`
 
## 获取推荐课程
说明：调用此接口，传入相应推荐类别`id`，可以获取推荐课堂列表数据

 **必选参数**：`id` : 今日秒杀4 热门推荐3 新课上线1 
 
 **可选参数**：`offset` `limit`  热门推荐可传offset,limit参数获取更多。
 
 **接口地址**：`/course`
 
 **调用例子**： `/course/recommend?id=4`  `/course/recommend?id=3&offset=21&limit=1`

## 获取课程类别下的列表
说明：调用此接口，传入栏目类别`tags`,可以获取课程类别下的列表数据

 **必选参数**：`tags` : 栏目类别id (栏目类别id值可用下面“获取标签请求”来查看)
 
 **可选参数**：`or`  新上线0  综合1 默认0
 
 **接口地址**：`/course/list`
 
 **调用例子**： `/course/list?tags=19`  `/course/list?tags=19&or=1`

## 获取标签
说明:调用此接口，可以获取相应类别的标签id值等

 **接口地址**：`/tag`
 
 **调用例子**： `/tag` 

## 获取课程详情
说明：调用此接口，传入课程`id`，可以获取课程详情

 **必选参数**：`id` :课程id
 
 **接口地址**：`/course/detail`
 
 **调用例子**： `/course/detail?id=1726` 

## 获取课程评论
说明：调用此接口，传入课程`id`，可以获取课程评论

 **必选参数**：`id` :课程id
 
 **可选参数**：`offset` `limit`  若总评论数大于20条，可以传参请求20后的数据
 
 **接口地址**：`/course/comments`
 
 **调用例子**： `/course/comments?id=1726` 
 
## 获取电子书数据
说明：调用此接口，可以获取电子书数据

 **接口地址**：`/ebooks`
 
 **调用例子**： `/ebooks` 
 
 ## 停更。。。(:3_ヽ)_