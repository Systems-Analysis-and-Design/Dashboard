## 软件架构文档：皮皮怪点餐

|版本|日期|描述|作者|
|---|---|---|---|
|草案|2018/5/29|本SAD主要从架构问题、解决方案说明、逻辑视图以及物理视图这四个部分来来描述此次项目的架构。|李辉旭、李佳|


### 架构设计

前后端分离开发，采用express框架，前端使用jade模型渲染网页页面，post数据表单到后台，后台使用node.js实现相应的操作对数据的处理。数据库采用mongodb数据库存取数据。

架构图（作者：李佳）

![架构图](/img/supplement/三层架构图.PNG)

### 解决方案


#### 技术备忘录：

1.问题：框架中循环+异步的执行使得mongodb数据库操作出错。

解决方案：将循环操作移动至数据库模型定义中，一次保存操作，不管修改多少条信息，只打开一次数据库，然后循环增删改，在最后一次循环时等待执行结束后关闭数据库，然后等待1000ms执行刷新当前页面。

动机：如果不解决这个问题，我们只能在一次保存中增加/修改/删除一条相关信息，这样的操作比较复杂，使用性能也不高。解决问题之后可以修改多条信息一次保存。这样的优势是显而易见的。

未决问题：同时增加多条信息由于循环异步问题会导致保存的多条信息都是最后一条的信息的复制。

其他可供选择的方案：使用Q的promise机制实现同步；或者使用async实现同步。

2.问题：循环操作使得数据库写入赋值出现问题。

解决方案：使用函数闭包，在每次循环中使用function(i)，保持每次的i值数据库操作不会被后续循环修改，解决了写入多条信息时数据重复的问题。

动机：如果不解决这个问题，我们在新建employee、menu时一次只能新建一条，点击保存写入数据库后再新建，不能同时新建多条一次写入。解决之后管理后台操作更加便捷。

3.问题：session问题，用户可以通过修改url直接进入他人账户。

解决方案：使用session判断机制，保存当前登录用户的session信息，并在每次get时进行判断，如果输入的或要跳转的不是本用户的页面地址，则强制跳转到本人主页。

动机：这个问题的后果显而易见，如果其他人可以通过url直接访问每个账户界面，那么毫无安全性可言，不能保证每家店的数据安全和私密。

未决问题：试图引入单点登录机制，使得同一个用户不能用时在线，但现在还没有找到更好的解决思路。

4.问题：第一次项目基本完成时，固定桌号和用户，不能动态查看其他店的信息。

解决方案：使用url绑定用户名和桌号，在后台管理个人主页新建生成二维码的功能，使用二维码访问不同的桌子，更贴近实际应用。

动机：如果不添加这个功能，我们就只能固定访问一个店的一个桌子的点菜界面，无法贴近实际点餐系统的逻辑。

### 逻辑视图

讨论和动机
我们此次的皮皮怪点餐系统采用的是经典的分层架构，整个系统比较简单，主要分为UI层，领域层以及技术服务层。
![逻辑视图](/img/supplement/逻辑视图.png)

### 物理视图

![物理视图](/img/supplement/物理视图.png)
