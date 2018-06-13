
### 1.返回状态码

|  类型  | stateCode | info |
| :--: | :-------: | :--: |
|  请求操作成功  |    200    | NULL |
|成功GET且文件未改变|304|NULL|
|页面重定向|302|NULL|
|  错误  |    500    | 错误信息 |

### 2.店主相关操作

| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
| /?op=regist | POST | 店主进行注册账户 | OK |
| /?op=managerLogin | POST | 店主登录 | OK |
| /user/?username={username}&info=personal|GET|获取店主个人主页|OK|
| /user/?op=logout| GET | 店主登出账户 | OK |
| /user/?username={username}&info=personal-account | POST | 店主修改个人信息 | OK |
|  /user/?username={username}&info=personal-store | POST | 店主修改商家信息 | OK |
|/user/?username={username}&info=ingredients | GET | 获取食材信息页面 | OK |
|  /user/?username={username}&info=ingredients | POST | 店主增加删除食材 | OK |
| /user/?username={username}&info=menu |GET| 获取菜品信息页面 | OK |
| /user/?username={username}&info=menu | POST | 修改菜品信息 | OK |
| /user/?username={username}&info=accounts | GET | 店主获取店铺的收支信息 | OK |
|/user/?username={username}&info=evaluation|GET|查看订单评价信息|OK|
|/user/?username={username}&info=employee|GET|获取员工信息页面|OK|
| /user/?username={username}&info=employee&op=save|POST|修改员工信息|OK|
| /user/?username={username}&info=employee&op=new|POST|新增员工|OK|
| /user/?username={username}&op=uploadImg | POST | 修改图片 | OK |
| /images/upload/{image_address} | GET | 加载新图片 | OK |


### 3.厨师相关操作
| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
|  /?op=employeeLogin | POST | 厨师登录 | OK |
| /employee/?username={username}&managername={managername} | GET | 显示订单界面 | OK |
| /employee/?username={username}&managername={managername} |POST | 更改订单状态 | OK |


### 4.顾客相关操作
| 路由  |  方法  |   说明     |  测试  |
| :--: | :-------: | :--: | :--: |
| /{managername}/client | GET | 顾客扫码登录获取菜单界面 | OK |
| /{managername}/client | POST | 顾客完成点餐后进入确认订单支付界面 | OK |
| /{managername}/handin/?id={streamid}&order={orderdetail}&tableID={tabelid} | GET | 顾客获取订单详情信息 | OK |
| /{managername}/handin/?id={streamid}&order={orderdetail}&tableID={tabelid}  | POST | 顾客确认支付 | OK |
| /{managername}/handin/?id={streamid}&order={orderdetail}&tableID={tabelid}&finish={true} | GET | 顾客获取订单评价界面 | OK |
| /{managername}/handin/?id={streamid}&order={orderdetail}&tableID={tabelid}&finish={true}  | POST | 顾客提交订单评价信息 | OK |



### 5.API示例说明---店主添加菜品
#### 5.1.应用场景
 店主在点餐系统中添加一项之前没有的菜品。
#### 5.2.接口示例
localhost:3000/user/?username=qqqqqq&op=uploadImg

localhost:3000/user/?username=qqqqqq&info=menu
#### 5.3.是否需要证书
 不需要
#### 5.4.请求参数
| 字段名 |  变量名  |   必填     |  类型  |  示例值 |  描述 |
| :--: | :-------: | :--: | :--: | :--: | :--: |
| 店主账号| owner | 是| string| qqqqqq | 店主用于管理该系统的账号|
| 菜名| name|是|string|麻辣香锅|新加菜品的名称|
|图片|imgSRc|否|string|images/upload/f.png|新加入的菜品的图片地址|
|菜品食材|ingredients|是|string|肉片、菜花|菜品的制作食材|
|菜品类别|class|是|string|rice|用于在点菜界面分类|
|菜品成本|cost|是|string|13|菜品的制作成本价|
|菜品售价|price|是|string|25|菜品的售价|


#### 5.5.举例如下
```
Menu {
  owner: 'qqqqqq',
  name: '水',
  imgSrc: 'images/upload/50d535e8fa166d1cfd92fa9c9a36ebaf.png',
  ingredients: '水',
  class: 'drink',
  cost: '3',
  price: '5',
 } 
 ```
 
#### 5.6.返回结果

| 字段名 |  变量名  |   必填     |  类型  |  示例值 |  描述 |
| :--: | :-------: | :--: | :--: | :--: | :--: |
|返回状态码|result|是|string|SUCCESS|添加菜品操作成功|


