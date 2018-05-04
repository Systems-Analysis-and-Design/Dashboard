# State_model

- 研究对象： 扫码点餐系统order的创建。

- 状态集合 S = { new order, landed, granted, selected, confirmed, invoiced, cancelled }

- 事件集合 E = { create order, land, change items, change items, select desks and food, grant, confirm, pay, invoice, cancel}

- 建模理由：先要有一个开始态和终止态。既然要把整个扫码用餐的流程包含在内，则需要一条主线流程，然后通过分支来表示其他不同情况，最后这些所有的情况都将汇集到终止态。

- 建模方法：

状态转换图：

![state_model](/img/state_model/state_model.png)
