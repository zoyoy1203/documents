# 外卖NodeJs版API——数据接口文档


## 注意：
1. 所有的请求都需要在`header`上携带token
2. 线上地址：http://zyuanyuan.com/elmApi
3. 在后面追加对应的接口地址即可使用

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

 **请求类型**：`post`
 
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
说明：调用此接口，可以获取美团外卖首页的分类名和图标

 **请求类型**：`get`
 
 **接口地址**：`/category`
 
 **调用例子**：`/category`
 
 
 
## 获取首页分类和banner数据

 **请求类型**：`get`
 
 **接口地址**：`/homeData`
 
 **调用例子**：`/homeData`
 
 
## 获取店铺列表
说明：调用此接口，可以获取商家店铺列表

 **请求类型**：`get`
 
 **必选参数**：`tag` 0:默认排序  1:销量  2:速度  3:评分  4:起送价最低  5:配送费最低

 **接口地址**：`/shop`
 
 **调用例子**：`/shop?tag=0`
 
 
## 获取店铺美食列表详情
说明：调用此接口，可以获取商家店铺美食列表数据

 **必选参数**：`id` 店铺id

 **接口地址**：`/shopFoods`
 
 **调用例子**：`/shopFoods?id=2`
 
## 获取店铺详情
说明：调用此接口，可以获取商家店铺详细信息

 **请求类型**：`get`
 
 **必选参数**：`id` 查询的店铺id

 **接口地址**：`/shopInfo`
 
 **调用例子**：`/shopInfo?id=1`
 
 
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
 
 **调用例子**：`/submitUserOrder`
 
 
## 用户订单付款

 **请求类型**：`post`
 
 **必选参数**：`order_id` 订单id
 
 **接口地址**：`/paying`
 
 **调用例子**：`/paying`


## 用户订单确认收货

 **请求类型**：`post`
 
 **必选参数**：`order_id` 订单id
 
 **接口地址**：`/orderEnd`
 
 **调用例子**：`/orderEnd`
