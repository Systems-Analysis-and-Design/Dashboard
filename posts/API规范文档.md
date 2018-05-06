
## 返回状态码

|  类型  | stateCode | info |
| :--: | :-------: | :--: |
|  成功  |    200    | NULL |
|  错误  |    400    | 错误信息 |

## 店主相关操作

| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
| /api/boss | POST | 店主进行注册账户 | OK |
| /api/boss/login{?openid} | GET | 检测店主是否登录 | OK |
| /api/boss/login | POST | 店主进行登录账户 | OK |
| /api/boss/logout | POST | 店主进行登出账户 | OK |
| /api/boss/self | DELETE | 店主注销自己的账户 | OK |
| /api/boss/manage/staff | POST | 店主添加员工账户 | OK |
| /api/boss/manage/staff/{staffname} | DELETE | 店主删除员工账户 | OK |
| /api/boss/manage/ingredients | POST | 店主添加某一种食品原材料 | OK |
| /api/boss/manage/ingredients/{ingredientsname} | DELETE | 店主删除某一种食品原材料 | OK |
| /api/boss/manage/ingredients/{ingredientsname} | PUT | 店主更新某种食品原材料的库存信息 | OK |
| /api/boss/manage/dishes | POST | 店主为店铺添加一种新的菜品 | OK |
| /api/boss/manage/dishes/{dishesname} | DELETE | 店主删除店铺中的某一种菜品 | OK |
| /api/boss/manage/remarks | GET | 店主获取客户的评价信息 | OK |
| /api/boss/manage/accounts | GET | 店主获取店铺的收支信息 | OK |


## 员工相关操作

| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
| /api/staff/login | POST | 员工登录 | OK |
| /api/staff/logout | POST | 员工登出 | OK |
| /api/staff/configure/{orderid}/orderconstate | PUT | 配置订单 | OK |
| /api/staff/complete/{orderid}/ordercomstate | PUT | 完成订单 | OK |

## 顾客相关操作

| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
| /api/cuetomer/login | POST | 顾客登录 | OK |
| /api/customer/createorder | POST | 顾客进店扫面点餐 | OK |
| /api/customer/showlist/orderid | GET | 顾客付款后跳转到的详细订单页面 | OK |

## 部分API说明
### 店主添加菜品
### 应用场景
 店主在点餐系统中添加一项之前没有的菜品。
 ### 接口链接
 https://api/boss/manage/dishes
 ### 是否需要证书
 不需要
### 请求参数
| 字段名 |  变量名  |   必填     |  类型  |  示例值 |  描述 |
| :--: | :-------: | :--: | :--: | :--: | :--: |
| 店主账号| bossid | 是| string| boss | 店主 用于管理该系统的账号|
| 店主账号密码| bosspassword|是|string|123456|店主登录到管理账户的密码|
|菜品名|dishname|是|string|mlxg|新加入的菜品的名称|
|菜品价格|dishprice|是|float|32.5|菜品的售出价格|
|菜品原料|dishingredients|是|string|xiaobaicai|制作该菜品所需要的原材料|
|菜品描述|dishdetial|否|string|delicious|描述该菜品的外观起源等信息|
### 举例如下
   <xml>
 
    <bossid>boss</bossid>
 
    <bosspassword>123456</bosspassword>
    
    <dishname>mlxg</dishname>
    
    <dishprice>32.5</dishprice>
    
    <dishingredients>xiaobaicai</dishingredients>
    
    <dishdetial>delicious</dishdetial>  
    
 </xml> 



