# 外卖NodeJs版API——数据接口文档


## 注意：
1. 所有的请求都需要在`header`上携带token
2. 线上地址：http://zyuanyuan.com/elmApi
3. 在后面追加对应的接口地址即可使用

## 主要技术栈
Node.js(koa2)+MySql

## 管理员登录获取token
说明：调用此接口，获取管理员token

 **请求类型**：`post`
 
 **必选参数**：`{"username":"admin","password":"123456"}`
 
 **接口地址**：`/adminLogin`
 
 **调用例子**：`/adminLogin`
 
## 获取管理员信息
说明：调用此接口，获取管理员信息

 **请求类型**：`post`
 
 **必选参数**：`token:**`
 
 **接口地址**：`/adminInfo`
 
 **调用例子**：`/adminInfo`
 
## 管理员登录注销
说明：调用此接口，退出登录

 **请求类型**：`post`
 
 **必选参数**：`token:**`
 
 **接口地址**：`/adminLoginout`
 
 **调用例子**：`/adminLoginout`
 
 
## 用户登录获取token
说明：调用此接口，获取管理员token

 **请求类型**：`post`
 
 **必选参数**：`username` `password`
 
 **接口地址**：`/userLogin`
 
 **调用例子**：`/userLogin`
 
## 获取用户信息
说明：调用此接口，获取管理员信息

 **请求类型**：`get`
 
 **必选参数**：`token:**`
 
 **接口地址**：`/userInfo`
 
 **调用例子**：`/userInfo`
 
## 用户登录注销
说明：调用此接口，退出登录

 **请求类型**：`post`
 
 **必选参数**：`token:**`
 
 **接口地址**：`/userLoginout`
 
 **调用例子**：`/userLoginout`

## 获取首页分类数据

 **请求类型**：`get`
 
 **接口地址**：`/category`
 
 **调用例子**：`/category`
 
 
## 获取首页分类和banner数据

 **请求类型**：`get`
 
 **接口地址**：`/homeData`
 
 **调用例子**：`/homeData`
 
 
## 获取所有店铺列表
说明：调用此接口，可以获取商家店铺列表

 **请求类型**：`get`
 
 **必选参数**：`tag` 0:默认排序  1:销量  2:速度  3:评分  4:起送价最低  5:配送费最低

 **接口地址**：`/shop`
 
 **调用例子**：`/shop?tag=0`
 
## 获取店铺分类标题列表
说明：调用此接口，可以获取指定店铺的美食分类列表

 **请求类型**：`get`
 
 **必选参数**：`shopid` 店铺id

 **接口地址**：`/shopCates`
 
 **调用例子**：`/shopCates?shopid=1`
 
 
## 获取店铺美食列表详情
说明：调用此接口，可以获取指定店铺美食列表数据，数据按类别分类

 **请求类型**：`get`

 **必选参数**：`id` 店铺id

 **接口地址**：`/shopFoods`
 
 **调用例子**：`/shopFoods?id=2`
 

## 获取店铺基础详情，美食列表不分类

 **请求类型**：`get`
 
 **必选参数**：`id` 店铺id

 **接口地址**：`/shopInfos`
 
 **调用例子**：`/shopInfos?id=2`
 
 
 
## 获取店铺详情
说明：调用此接口，可以获取商家店铺详细信息

 **请求类型**：`get`
 
 **必选参数**：`id` 查询的店铺id

 **接口地址**：`/shopInfo`
 
 **调用例子**：`/shopInfo?id=1`
 
## 获取店铺订单评论数据

 **请求类型**：`get`
 
 **必选参数**：`shopid` 查询的店铺id

 **接口地址**：`/shopComment`
 
 **调用例子**：`/shopComment?shopid=1`
 
 
## 获取所有订单信息

 **请求类型**：`get`

 **接口地址**：`/allOrder`
 
 **调用例子**：`/allOrder`
 
 
## 修改指定店铺信息

 **请求类型**：`post`
 
 **必选参数**：
 ```
 {
	id:"店铺id"
	shop_name:"店铺名",
	shop_score:"店铺评分",
	month_sales:"月售",
	pic_url:"店铺封面图",
	delivery_time:"送货时间",
	min_price:"起送价格",
	shipping_fee:"配送价格",
	average_price:"人均价格",
	address:"地址",
	bulletin:"公告",
	status:"状态码 0:非营业 1：营业中"
}
 
 ```

 **接口地址**：`/updateShopInfo`
 

 
## 创建店铺

 **请求类型**：`post`
 
 **必选参数**：
 ```
{
	name:"店铺名",
	pic_url:"店铺封面图",
	delivery_time:"送货时间",
	min_price:"起送价格",
	shipping_fee:"配送价格",
	address:"地址",
	bulletin:"公告"
}
 
 ```

 **接口地址**：`/createShop`
 

 
 
## 添加店铺美食分类

 **请求类型**：`post`
 
 **必选参数**：
 ```
{
	shop_id:"店铺id",
	name:"分类名"
}
 
 ```

 **接口地址**：`/addShopFoodCate`
 

 
 
## 修改指定美食信息

 **请求类型**：`post`
 
 **必选参数**：
 ```
{
	id:"美食id",
	cate_id:"分类id",
	title:"美食名称",
	desc:"介绍",
	cover:"封面图",
	month_sales:"月售",
	like:"点赞",
	origin_price:"原价",
	sell_price:"售价"
}
 
 ```

 **接口地址**：`/updateShopfood`
 

 
 ## 删除指定美食

 **请求类型**：`post`
 
 **必选参数**：
 ```
{
	id:"美食id"
}
 
 ```

 **接口地址**：`/delFood`
 

 
 ## 创建添加美食

 **请求类型**：`post`
 
 **必选参数**：
 ```
{
	shop_id:"店铺id",
	cate_id:"分类id",
	title:"美食名称",
	desc:"介绍",
	cover:"美食封面图",
	month_sales:"月售",
	like:"点赞",
	origin_price:"原价",
	sell_price:"售价"
}
 
 ```

 **接口地址**：`/addFood`


 
## 获取用户地址信息

 **请求类型**：`get`

 **接口地址**：`/userAddress`
 
 **调用例子**：`/userAddress`
 
 
## 提交用户订单

 **请求类型**：`post`
 
 **必选参数**：`order`
 ```
 {
	shop: {shop_id: 1, shop_name: "串串（F区泡泡店）", shipping_fee: 1, delivery_time: 44},
	user: {username: "zyy", gender: "女士", phone: "12345678912", address: "阳光大道22号"},
	foods:[
		{
			id: 4
			title: "大肉串"
			desc: "欢迎下单品尝"
			cover: "https://p0.meituan.net/xianfu/2aec31be8f8b293e4246184633ee055d404255.jpg@150w_150h_80Q_0e_1l.webp"
			month_sales: 100
			origin_price: 4
			sell_price: 4
			discount: null
			count: 2
		},
		{
			id: 5
			title: "金丝鸡柳"
			desc: "欢迎下单品尝"
			cover: "https://p1.meituan.net/wmproduct/935daa876353f22edf6488e644967399863147.jpg@150w_150h_80Q_0e_1l.webp"
			month_sales: 100
			origin_price: 3
			sell_price: 3
			discount: null
			count: 1
		}
	],
	totalPrice: 14
 }
 ```

 **接口地址**：`/submitUserOrder`

 
 
## 用户订单付款

 **请求类型**：`post`
 
 **必选参数**：`order_id` 订单id
 
 **接口地址**：`/paying`
 


## 用户订单确认收货

 **请求类型**：`post`
 
 **必选参数**：`order_id` 订单id
 
 **接口地址**：`/orderEnd`
 
 
 
## 获取用户全部订单

 **请求类型**：`get`
 
 **必选参数**：`user_id` 用户id
 
 **接口地址**：`/allOrder`
 
 **调用例子**：`/allOrder?user_id=1`
 
 
## 获取用户未评价订单

 **请求类型**：`get`
 
 **必选参数**：`user_id` 用户id
 
 **接口地址**：`/needCommitOrder`
 
 **调用例子**：`/needCommitOrder?user_id=1`
 

## 提交用户订单评价

 **请求类型**：`post`
 
 **必选参数**：
 ```
 {
	order_id:"订单id",
	user_id:"用户id",
	value:"评分",
	comment_text:"评论内容"
 }
 ```
 
 **接口地址**：`/userComment`
 

 