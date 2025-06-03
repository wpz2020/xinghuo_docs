  * [](/)
  * 功能示例项目
  * 拼接地图Demo使用说明

复制链接

本页总览

# 拼接地图Demo使用说明

星火编辑器为开发者提供了动态拼接场景的功能和Demo，本文档介绍Demo的基本实现：

### 选择场景属性中的『预制地块』开启功能[​](/Manual/Demo/SpliceScene#选择场景属性中的预制地块开启功能
"选择场景属性中的『预制地块』开启功能的直接链接")

选中左侧场景列表中的场景，勾选『预制地块』，则会在场景上自动生成4个预制地块，其命名为『top』（上）、『bottom』（下）、『left』（左）、『right』（右）

在当前的实现逻辑中，这四个地块会自动吸附地图边缘

![](https://doc.sce.xd.com/assets/images/拼接场景Demo_1-db11b0085bbfff8fe981e7d126db8c7e.png)

### 为『预制地块』配置通行的模型[​](/Manual/Demo/SpliceScene#为预制地块配置通行的模型
"为『预制地块』配置通行的模型的直接链接")

选中预制地块后，右上角有『通行配置』选项，可以选择默认的三种配置，也可以自己配置自己需要的模型。
这一配置代表的是『拼接两个场景的模型』，例如Demo中选择了木桥的模型作为拼接的模型。

![](https://doc.sce.xd.com/assets/images/拼接场景Demo_2-7ab7ff0091403cf41f6d4bd4a12b77aa.png)
![](https://doc.sce.xd.com/assets/images/拼接场景Demo_3-8d6db67a6e3fe21480c9ad9ba42a5823.png)

### 核心逻辑一：在服务端进行场景拼接[​](/Manual/Demo/SpliceScene#核心逻辑一在服务端进行场景拼接
"核心逻辑一：在服务端进行场景拼接的直接链接")

加载场景后，在服务端触发中进行场景的拼接  
例如下图所示

![](https://doc.sce.xd.com/assets/images/拼接场景Demo_4-430d02717723f2e2dd7029d578e22635.png)

###
核心逻辑二：在客户端根据进入场景的事件，动态的显示拼接场景[​](/Manual/Demo/SpliceScene#核心逻辑二在客户端根据进入场景的事件动态的显示拼接场景
"核心逻辑二：在客户端根据进入场景的事件，动态的显示拼接场景的直接链接")

（当然你也可以在一开始就把这些场景都拼接好）

![](https://doc.sce.xd.com/assets/images/拼接场景Demo_5-b17ef104a6f2d4a00c05c7c7361bb0ba.png)

### 注意：当前需要了解的信息：[​](/Manual/Demo/SpliceScene#注意当前需要了解的信息
"注意：当前需要了解的信息：的直接链接")

  1. 拼接场景暂时只支持同样场景大小的拼接。
  2. 细心看，Demo中的桥会在进入时创建一次，从另外一侧进入时，会再创建一次。这是由于现在的写法非常简单，不用维护『桥是否存在』的逻辑。实际上我们也不希望开发者花时间进行相关逻辑的维护，我们会在后续更新中提供判断『桥是否存在』触发语句。

### Demo下载地址[​](/Manual/Demo/SpliceScene#demo下载地址 "Demo下载地址的直接链接")

链接: <https://pan.baidu.com/s/1cJPyc__STw3F3Ikmx4Q8VA?pwd=SCED> 提取码: SCED

[上一页示例与教学](/Manual/Demo/Intro)[下一页精美国风场景示例及使用方法](/Manual/Demo/SceneExamples)


