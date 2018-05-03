
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
