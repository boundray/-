# 驾驶陪练小程序
## 开发环境和框架：
系统建模采用微信小程序官方提供的开发环境，系统框架采用微信小程序官方提供的MINA框架。

## 开发语言与数据库：
系统实现语言前端采用JSON、Javascript、wxml、wxss 混合编程，数据库采用JSON数据。
# 系统数据库设计
![image](https://user-images.githubusercontent.com/129675370/229617322-954747e3-8257-433e-a745-32d315dcb2ad.png)
# 类设计说明
## 个人信息(MyInformation)类设计说明：

### 属性说明：

(1)姓名(name)
①定义：登录者的姓名
②类型：String

(2)性别(Sex)
①定义：登录者的性别
②类型：String
③可选取值：Male,Female

(3)年龄(Age)
①定义：登录者的年龄
②类型：int
③取值范围：(0,100)


## 新手司机(Driver)类设计说明:

### 属性说明

(1)车型(uservehicletype)
①定义：新手司机所期望使用的车辆型号
②类型：String

(2)司机驾照ID(userIDnumber)
①定义：新手司机上传的驾照的ID号
②类型：String

(3)用户ID(userID)
①定义：新手司机在系统中的编号
②类型：String

(4)用户名(nickname)
①定义：新手司机在系统中的编号
②类型：String

### 方法说明

(1) 获取新手司机信息(getDriverInfo)
功能：返回新手司机的个人信息
参数：userID
返回值：true/false

## 陪练员(Coach)类设计说明

### 属性说明

(1)陪练员驾照ID(coachIDnumber)
①定义：陪练员上传的驾照的ID号
②类型：

(2)陪练员ID(coachID)
①定义：陪练员在系统中的编号
②类型：String

(3)价格(price)
①定义：陪练员陪练一小时的价格
②类型：int

(4)空闲时间段(freetime)
①定义：陪练员一天中可以陪练的时间段
②类型：String

(5)星级(star)
①定义：根据历史订单评价得出的陪练员的陪练星级
②类型：int

### 方法说明

(1) 选择陪练员(SelectCoach)
功能：返回符合条件的陪练员信息
参数：coachID
返回值：string[]

## 管理员(Admin)类设计说明

### 属性说明

(1)职工号(adminID)
①定义：管理员在系统中的编号
②类型：String

### 方法说明

(1) 审核帖子(CheckPost)
功能：返回审核通过的帖子
参数：postID
返回值：true/false

## 陪练订单(Order)类设计说明

### 属性说明

(1)预约时间(time)
①定义：新手司机在此订单中预约练习的时间
②类型：String

(2)评价(Evaluation)
①定义：新手司机对于该订单的打分
②类型：int

### 方法说明

(1) 创建新预约订单(CreateNewReservation)
功能：创建一条新的订单记录
参数：userID,coachID
返回值：true/false

## 车辆(Vehicle)类设计说明

### 属性说明

(1)车牌号(license)
①定义：车辆的车牌号
②类型：String

(2)型号(coachvehicletype)
①定义：车辆的型号
②类型：String

(3)保险(insurance)
①定义：车辆的保险
②类型：String

### 方法说明

(1) 获取车型(getVehicleInfo)
功能：返回车辆型号
参数：coachID
返回值：vehicletype

## 地点(Spot)类设计说明

### 属性说明

(1)类型(spottype)
①定义：地点的类型
②类型：String
③可选取值：“上车点”，“下车点”

(2)名称(spotname)
①定义：地点的名称
②类型：String

### 方法说明

(1) 选择地点(SelectSpot)
功能：返回用户输入的上车点和下车点
参数：null
返回值：boarding,dropoff

## 陪练项目(Project)类设计说明

### 属性说明

(1)项目名称(projectname)
①定义：陪练项目的名称
②类型：String

(2)项目内容(projectcontent)
①定义：陪练项目的具体介绍内容
②类型：String

(3)项目ID(projectID)
①定义：陪练项目在系统中的编号
②类型：String


## 帖子(Post)类设计说明

### 属性说明

(1)发帖时间(posttime)
①定义：新手司机发帖的时间
②类型：String

(2)点赞数(likecount)
①定义：帖子收到的点赞数量
②类型：int

(3)标题(posttitle)
①定义：帖子的标题
②类型：String

(4)帖子内容(postcontent)
①定义：帖子的具体内容
②类型：String

(5)帖子ID(postID)
①定义：帖子在系统中的编号
②类型：String


### 方法说明

(1) 发布帖子(CreatePost)
功能：创建一条新的帖子记录
参数：postID
返回值：true/false

## 点赞(Like)类设计说明

### 属性说明

(1)点赞时间(liketime)
①定义：新手司机点赞的时间
②类型：String

(2)点赞ID(likeID)
①定义：新手司机的点赞在系统中的编号
②类型：String

### 方法说明

(1) 添加点赞(CreateLike)
功能：创建一条新的点赞记录
参数：postID
返回值：true/false

## 评论(Comment)类设计说明

### 属性说明

(1)评论时间(commenttime)
①定义：新手司机评论的时间
②类型：String

(2)评论内容(commentcontent)
①定义：新手司机评论的具体内容
②类型：String

(3)评论ID(commentID)
①定义：新手司机的评论在系统中的编号
②类型：String

### 方法说明

(1) 添加评论(CreateComment)
功能：创建一条新的评论记录
参数：postID
返回值：true/false

# 界面说明
## 首页（MainWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229620822-977adb80-3a6d-4160-a591-39835ab6531a.png)

首页会有三个分栏，便于用户根据需求筛选陪练员
## 陪练员详细信息（CoachWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229621029-3aec28c4-a9f8-40c5-9a66-d13bbdc26a02.png)

如上图所示，陪练员的详细信息被显示在页面上。

点击“在线联系”——用户可以在聊天界面与陪练员联系。

点击“预约”——用户可以填写上下车地点、选择项目类别和时间。
## 聊天界面（ChatWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229621169-f9b8afad-62c7-4907-a84e-71030beec0ec.png)

如上图所示，用户可以与陪练员在线聊天。

点击“预约”——用户可以填写上下车地点、选择项目类别和时间。
## 社区界面（CommunityWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229621242-c911e9b6-30af-4bb8-b0b7-5422ec6b58f9.png)
![image](https://user-images.githubusercontent.com/129675370/229621265-6d948c7a-6511-4792-9274-8ca58d58c0c3.png)
![image](https://user-images.githubusercontent.com/129675370/229621346-fd7b77f3-b939-4507-8a89-7699d9e2ab82.png)

如上图所示，社区界面分为“资讯”和“车友圈”两个板块。

在“资讯”板块，用户可以点击资讯查看内容详情。

在“车友圈”板块，用户可以发帖并对其他帖子点赞、评论。
## 预约界面（ReservationWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229621444-3e30fee9-4bb6-4b47-9c37-e874222397f9.png)
![image](https://user-images.githubusercontent.com/129675370/229621500-3cf6bd6d-b4b0-4e00-a101-f325183ddb14.png)

如上图所示，地图被显示在页面上供新手司机查看周围地点，用户可以填写上下车地点、选择项目类别和时间。

点击“提交”——用户被提示“是否确认预约”，若点击确定键，则预约成功。
## 5.17.我的（DriverWindow）设计说明
![image](https://user-images.githubusercontent.com/129675370/229621570-4128a3ec-7144-4a5d-bcb6-1d10332d31b6.png)

如上图所示，用户的头像和用户名会被显示在页面上方。

点击“个人资料”——用户可以查看并完善自己的个人信息
![image](https://user-images.githubusercontent.com/129675370/229621656-f1e7b600-fbce-4556-b649-9a51677af092.png)

点击“历史订单”——用户可以查看自己曾经预约过的订单，点击“评价”可以对陪练订单进行打分。
![image](https://user-images.githubusercontent.com/129675370/229621717-9a8b7310-2788-4754-8b4b-abe24f410703.png)
![image](https://user-images.githubusercontent.com/129675370/229621735-1fea2129-4369-473c-96ff-745afc26b978.png)

点击“我的点赞”——用户可以查看自己曾经点赞过的帖子

点击“我的帖子”——用户可以查看自己发布过的帖子

![image](https://user-images.githubusercontent.com/129675370/229621798-ed5829f4-f6d5-4363-bfa3-06406026f56c.png)

点击“退出”——用户退出小程序

![image](https://user-images.githubusercontent.com/129675370/229621855-8c60f951-1f86-4173-9392-fa5f4221350a.png)
