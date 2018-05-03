
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
