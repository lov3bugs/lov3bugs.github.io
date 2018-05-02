---
title: HandLog
date: 2018-04-15
tags: 日记
---
What is your main focus for today?
 <!-- more -->

## 2018-05

---

### 2018-05-02

1. 五一假期BUG跟进
  - 会员续费生效时间设置，生效的截止日期设置为0429/0430，实现的截止日期为当天8：00。
    而商品的生效时间，设置开始日期为0501，实际修改学生状态是在0502。
  - 母亲节活动有个学生的手机号要修改

2. Staging新题型项目测试
  * 学生APP不能上传照片 # 合并代码之后未重现
  * 讲师APP查看学生错题列表 前端报错 # 已解决
  * 学生APP新题型选择题，选择正确答案再取消选择，答错判对
  * 讲师统一作业，抽题接口返回的题目属性缺少subjectId，导致加入购物车报错空指针 # 已解决
  * 讲师APP，部分页面点击加题，会更新两次购物车 # 待确认

3. 日程
```
10-11：假期反馈BUG
11-12：回归讲师APP BUG
14-15：最后一轮全流程测试；学生APP代码merge
15-16：最后一轮全流程测试-讲师布置新题型作业
16-17：最后一轮全流程测试-学生完成新题型作业
17-18：最后一轮全流程测试-讲师查看新题型作业

```

---
---

## 2018-04

---

### 2018-04-30

1. 学车
  * 上车三件事：座椅膝盖距离、座椅手臂距离、安全带
  * 发动四件事：打开左转向灯、踩离合刹车、挂挡、松手刹
  * 离合：踩要一踩到底、放要一快一慢（）
  * 刹车：同时踩离合和刹车，离合一踩到底，踩刹车先轻后重，直到停稳松开
  * 方向盘：左右各一圈半，双手手心贴住方向盘，手指放松，大拇指靠在内侧
2. 心理学知识结构
3. 学习进度 **可视化** 研究 # 未开始

---

### 2018-04-29

1. 心理学的研究内容和研究方法
2. 学习方法

---

### 2018-04-28

1. Staging学生新题型作答的不同场景

2. 讲师端 交互优化
  * 新题型抽题排序，抽到的题目是普通词汇语法未作排序（根据多个知识点的每个一题进行排序）
  * 预览套题-题目详情页面加入购物车 报错；统一作业加题的列表和详情页 加入购物车也报错
  * 讲师APP作业列表，上拉翻页，结果只展示下一页的内容
  * 讲师作业列表 PC跟APP的接口分开，PC支持查全部班级的作业，APP只查单个班级
  * （第一点）词汇语法加题逻辑，新增根据知识点的排序跟原来按布置过、加入购物车的排序冲突

3. 日程
```
11-12: 准备抽题数据，加题时能抽出新题型的数据
14-15：抽题交互验证
15-16：回归讲师APP BUG
16-17：讲师APP 交互
17-19：回归讲师APP BUG
```

---

### 2018-04-27

1. 确认staging布置新题型，学生launch数据为空的BUG

2. Staging新题型项目测试
* 讲师布置作业，学生都可以正常打开
* 订正也正常打开，可继续订正直到全对
* 讲师不能查看新题型的作业完成情况，个人和班级都不行

3. 日程
```
10-11: staging布置新题型作业流程测试（布置-答题-订正-强化）
11-12：staging导入听力音频材料；准备统一作业新题型数据
14-15：讲师APP查看学生新题型作业答题情况
15-16：回归BUG
16-17：讲师APP查看学生新题型作业BUG已修复，验证
17-18：BUG评审
```

---

### 2018-04-26

1. 确认学生APP代码merge到master，发布staging

2. Staging新题型项目测试
* 管理端预览套题 接口需要调整
* 学生端打开新题型的作业，launch数据异常，缺少题目信息
* 上面的问题修复之后，重新布置同义选择和单句选词，同义选择作业有数据，单句选词没有数据
* 上面布置的同义选择作业，订正launch报错500
* 重要的遗留问题：布置作业新题型题目数据为空

3. 日程
```
10-11：布置新题型作业报错BUG，因为新题型文章没有UnitId -- 已解决
11-12: Staging新题型、文章、题目导入、套题创建
14-15：学生launch新题型作业数据为空；staging准备不同题型的套题数据
15-16：讲师APP布置套题，（↑学生launch为空的问题，是布置作业的数据为空，已修复）；
16-17：学生APP作业答题订正、错题复习练习
17-19：BUG评审
20：微服务接口504 环境异常
```

---

### 2018-04-25

1. Test新题型项目回归测试
* 讲师布置套题-所有题型套题
* 讲师布置统一作业
* 学生提交作业
* 学生完成订正
* 学生强化练习
* 学生错题本复习/练习
* 讲师查看班级完成情况
* 讲师查看学生完成情况

2. Staging新题型项目测试
- UBJ未部署
- 学生APP代码什么时候merge到master

3. Onedrive部分文档迁移到HexoBlog
* 个人总结

---

### 2018-04-24

1. Test新题型项目测试
* 问题
> 讲师APP 套题列表 选择单元进度点击无响应 y
  讲师APP 新题型题目列表页&详情页面展示 n y
  ！讲师APP 预览购物车的视频听力题，列表上不能点击查看视频题，但是可以播放视频 n
  讲师APP 选择题目详情页面 右上角加入按钮无响应 n y
  讲师APP 统一作业选择知识点 全选/取消全选 显示样式 n y
  讲师APP 选择题目列表页面 同时播放多个视频 n
  讲师APP 统一作业 未选单元可以点击确定 抽题接口报错

2. 母亲节活动更新（学生APP热更新）
- 班级成绩开关
- 母亲节活动页面
- 人机对话 待确认

3. 速递易DX2561

---

### 2018-04-23

1. Test新题型项目测试
+ 管理端创建、预览套题 》 新题型发布后不能预览
+ 学生端答题 - 答题功能，作业分数，班级平均分，芝士币，经验值，错题本
+ 讲师端异步统计信息 - 作业完成情况，正确错误答案统计，订正完成统计
+ 抽题：（准备单元-知识点数据）
  * 统一作业：抽题需要根据不同知识点排序
  * 个性化作业：排除新题型 Y
  * 强化练习：排除新题型
+ 学生APP页面
  * 作业答题&review y
  * 订正答题&review y
  * 错题复习列表&详情 y
  * 错题巩固练习 n
  * 错题收藏专练
  * 错题单元专练 n
  * 错题刷题狂 n
+ 讲师APP页面
  * 布置套题流程 Y
  * 布置统一作业流程 》 准备数据
  * 布置作业预览列表&详情 》 新题型要求显示备选词
  * 查看作业列表&成绩单 Y
  * 查看班级错题列表&详情 列表Y 详情N
  * 查看学生错题列表&详情 列表Y 详情N
- 微信教师通&家长通

+ 异常流
  * 管理员重置作业 n 已修复 y

2. Hexo+Travis CI

---

### 2018-04-20

0. 母亲节活动上线遗留BUG
0.1 预览贺卡学生姓名显示为空
0.2 iOS emoji表情兼容问题，全输入表情后，前端判断字符数超过了100，显示还可输入-11个字符

1. Test新题型项目测试
+ 学生端答题 - 作业分数，班级平均分，芝士币，经验值，错题本
+ 讲师端异步统计信息 - 作业完成情况，正确错误答案统计，订正完成统计
+ 抽题：（准备单元-知识点数据）
  * 统一作业：
  * 个性化作业：
- 学生APP页面
  * 作业答题&review y
  * 订正答题&review y
  * 强化答题&review ？
  * 错题复习列表&详情 y
  *
- 讲师APP页面
  * 布置套题 Y
  * 布置统一作业
  * 查看作业列表&成绩单 Y
  * 查看班级错题列表&详情 列表Y 详情N
  * 查看学生错题列表&详情 列表Y 详情N

2. 人机对话交互讨论
>问题：
- 进入题目，下载音频，网络影响比较大
- 部分音频不能播放，没有出现倒计时进度条
- 音频播放会卡顿，只播放一半
- 答题卡切题问题
- 使用口语很卡（朱瑶）
- 口语答题时间变长（老师）

>结论：
1. 确定APP版本 2.11.0已经发布 --之后具体关注新版本的问题
2. 答题卡切题 --优化，答题过程中不允许切题/隐藏答题卡
3. 口语音频上传队列展示 --不展示
4. 部分口语题分数和颜色标记 --作bug修复，只根据最终展示分数标记，多小题的统一标记同一颜色
5. 学生APP框架改为react native 还是全native --暂不修改
6. 前端微信工程 --之后考虑教师通、家长通改版，暂不支持口语新题型展示

3. 母亲节活动兼容性统计
- PC：
> Win10 Chrome版本 64.0.3282.140（正式版本） （64 位）

- APP：
> Nexus 6P，Android 8.0
  Xiaomi 6，Android 7.1.1

---

### 2018-04-19
---

- 休息

### 2018-04-18

0. 母亲节活动PC端测试
- 练习册跳转
- 数据埋点

1. APP准备发布：母亲节活动&人机对话

2. Test新题型项目测试

3. 开票
抬头：上海汉得知云软件有限公司
税号：310107336448300
金额：￥2000
日期：2018-04-01
内容：餐饮费
收件地址：上海市普陀区真北路958号天地科技广场一号楼203
手机号：17701860729

4. 上线
4.1 活动页面第一次打开预览贺卡，姓名不能显示
4.2 留言输入框，输入表情后，提示还有-11个字符可输入
4.3 分享之后的图标不显示

---

### 2018-04-17

0. 学生APP发布邮件 y

1. Test新题型项目测试
- 1.1 管理端创建文章、导入题库、创建套题、创建测试
- 1.2 讲师预览套题、布置套题、（统一作业）选择题目、布置个性化作业
- 1.3 学生打开作业、作业订正、强化练习、错题练习

2. 新人培训
Web role：管理员、讲师、学生、校长
APP role：讲师、学生
wechat role：讲师、家长
Services：作业中心、练习册、错题本、消息中心、奖品中心、积分系统、微课堂、会员付费

3. 线上BUG
- 3.1 生日选择199x，实际保存的是22xx年
- 3.2

---

### 2018-04-16

0. 上周五面试结果： 预约两人，实到一人（廖雅军） y
- 0.1 项目经验：两年外包公司功能测试，四个项目主要是Web后台管理
- 0.2 教育经历：西南科技大学 本科 软件工程
- 0.3 自主学习：自动化测试
- 0.4 思维意识：质疑

1. 学生APP发布安卓市场 y

2. Dev新题型项目测试
- 2.0 导入题库，创建套题
- 2.1 讲师布置作业
a. 套题加入购物车直接布置 y
b. 套题加入购物车预览布置 n
- 2.2 学生打开作业
a. 作业原题 y
b. 作业订正 y
c. 强化练习 y
d. 错题本复习/练习 n
- 2.3 讲师查看成绩
a. 班级成绩列表/详情 n
b. 学生成绩列表/详情 n

3. 人机对话测试报告 n

---

### 2018-04-15

0. 完成hexo blog搭建
- 0.1 hexo本地环境准备
- 0.2 添加github同步
- 0.3 提交blog内容，hexo g&hexo d
- 0.4 hexo theme设置

1. 测试并提交学生APP审核
- 1.1 母亲节活动
> 保存手机号；
  预览贺卡，生成贺卡（白银宝箱）；
  完成练习（黄金宝箱）；
  分享活动；
  分享页面唤醒APP；

- 1.2 人机对话优化：得分调整和BUG修复
> 云知声接口相关题型，分数增加：
  > 低于20分，不做处理，分数=原始分数；
    多小题题型，分数=原始分数开方*10；
    单小题题型，分数=原始分数加二十的开方*10；
  BUG修复:
  > iOS 连续点击录音按钮 页面卡死；

- 1.3 注册功能
> 学生注册账号：手机号+图片验证码+短信验证码+密码+班级号+姓名+性别+生日；
  注册完成自动加入班级；
  加入班级后的作业和练习，异步绑定给学生；
  个人中心增加加入班级功能；
  个人中心生日为空的，可重新设置生日；

- 1.4 APP其他功能回归
> 作业中心；
  练习册；
  错题本；
  微课堂；
  奖品中心；
  个人中心；
  消息中心；
  **全题型**；

2. Amazon return
- *未完成*

3. 物理学回顾
- *未完成*

---