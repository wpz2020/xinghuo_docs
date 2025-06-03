  * [](/)
  * 界面编辑器
  * 常用界面控件介绍
  * Buff列表

复制链接

本页总览

# Buff列表

Buff列表可以在界面中显示主控单位拥有的所有Buff信息，可以显示各Buff的刷新时间、图标、叠加层数和提示。

![](https://doc.sce.xd.com/assets/images/BuffList-d1d3504797c449d82581d92ba813d5e5.png)

### 属性列表[​](/Manual/UIEditor/Components/BuffList#属性列表 "属性列表的直接链接")

属性| 功能  
---|---  
Buff分类过滤| 筛选在UI上显示的Buff分类，用分号（;）隔开，如果不填则全部显示  
Buff图标模板| 设置Buff图标的模板，是一个Lua UI，默认为@gameui.prefab.buff.buff_icon  
Buff宽度| 设置Buff图标的宽度  
Buff极性| 筛选在UI上显示的Buff极性分类，用分号（;）隔开，如果不填则全部显示  
Buff间隔| 设置Buff图标之间的间隔  
Buff高度| 设置Buff图标的高度  
预览用正面/负面/无极性Buff个数| 调整在界面编辑器中用于预览的Buff数量  
  
### 事件[​](/Manual/UIEditor/Components/BuffList#事件 "事件的直接链接")

事件| 功能  
---|---  
排序函数| 可以指定Buff列表中Buff的排序规则，返回一个**布尔** 类型  
  
### 用法[​](/Manual/UIEditor/Components/BuffList#用法 "用法的直接链接")

Buff列表的使用无需触发器干预，将Buff列表放在UI中，游戏时会显示当前主控单位所有符合要求的Buff信息。

### Buff图标[​](/Manual/UIEditor/Components/BuffList#buff图标 "Buff图标的直接链接")

除了使用Buff列表绑定主控单位的所有Buff外，也可以使用Buff图标绑定并显示单个Buff的信息，该控件与Buff列表的单个图标表现一致。

![](https://doc.sce.xd.com/assets/images/BuffIcon-ebccb87fc482d45952fe05dee5cec16c.png)

### Buff描述[​](/Manual/UIEditor/Components/BuffList#buff描述 "Buff描述的直接链接")

在Buff列表以及Buff图标中，可以添加Buff描述控件来实现点击图标后显示该Buff描述的功能。

![](https://doc.sce.xd.com/assets/images/BuffDescExample-1cf8fdd2e7919bb6b3cc87cecc2f1ccf.gif)

使用Buff描述控件时，必须把该控件放到Buff列表或Buff图标的**子控件** 中，如图所示：

![](https://doc.sce.xd.com/assets/images/BuffDesc_1-099486030e7dad5bedd0a671340a421a.png)

此外，还需要在数据编辑器中，配置Buff的描述文本。如果描述文本为空，点击Buff图标不会出现任何描述提示。

![](https://doc.sce.xd.com/assets/images/BuffDesc_2-7afe6ee7ee0bffd1cd3f627ca2a25592.png)

**标签：**

  * [界面编辑器](/tags/界面编辑器)
  * [UI控件](/tags/ui控件)
  * [Buff](/tags/buff)

[上一页可附着面板](/Manual/UIEditor/Components/AttachablePanel)[下一页UI场景](/Manual/UIEditor/Components/UIScene)


