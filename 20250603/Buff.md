  * [](/)
  * 游戏机制与交互
  * Buff

复制链接

本页总览

# Buff

Buff是游戏中的一种状态，可以实现对单位属性的修改、添加粒子特效、响应伤害等为单位添加状态的操作。

## 创建Buff[​](/Manual/GameMechanics/Buff#创建buff "创建Buff的直接链接")

使用Buff前，需要在数据编辑器中创建或添加一个Buff蓝图节点。一个典型的Buff节点如下图所示：

![](/assets/images/掉血200-98786f4b0d098a5b4fc84d78ca028f0d.png)

### Buff节点说明[​](/Manual/GameMechanics/Buff#buff节点说明 "Buff节点说明的直接链接")

  1. 在[持续时间]开始前，执行[初始效果]链接的效果。

  2. 在[持续时间]内，提供[属性加成]。

  3. 在[持续时间]内，添加一些[单位状态]。

  4. 在[持续时间]内，移除一些[单位状态]。

  5. 在[持续时间]结束时，执行[完成效果]链接的效果。

  6. 在每个[周期]结束时，执行一个效果

  7. 刷新时效果：同一个目标单位身上被同一个施法者重复添加同一Buff的时候执行一个效果。

比如目标单位身上先有一层”伤害加深Buff“，然后在Buff还没消失时，同一施法者又对目标单位再次附加了伤害加深，此时就会引发刷新效果。

  8. 在Buff所在单位身上，不再有来自同一施法者的同名Buff时，执行[全部移除后效果]链接的效果。

## 使用Buff的案例[​](/Manual/GameMechanics/Buff#使用buff的案例 "使用Buff的案例的直接链接")

接下来我们分别通过几个案例来学习它的使用：

### 通过添加Buff修改单位的属性[​](/Manual/GameMechanics/Buff#通过添加buff修改单位的属性
"通过添加Buff修改单位的属性的直接链接")

这里我们以为单位添加Buff后会损失200生命值，Buff被移除后生命恢复为例：

首先需要通过标准Buff模板，创建一个数编蓝图

![](/assets/images/掉血200-98786f4b0d098a5b4fc84d78ca028f0d.png)

这里我们为它添加一个粒子表现来方便查看效果

![](/assets/images/加个粒子表现-10ac4bfe4cbde759cfa31c7b28634bb5.png)

然后在数编中配置对应的技能

![](/assets/images/减血技能-7f625e49946b60f3523f6ce56d834e5e.png)

接下来查看效果：

单位被添加Buff后：

![](/assets/images/成功掉血-6005503cd02d76b98ea59cd7ee317275.png)

当Buff被移除后：

![](/assets/images/血量回复-5abaaf0cf468c5dd837c9d7dce889636.png)

### 通过为单位添加Buff造成持续伤害[​](/Manual/GameMechanics/Buff#通过为单位添加buff造成持续伤害
"通过为单位添加Buff造成持续伤害的直接链接")

我们可以为单位添加负面Buff，让其每秒受到指定伤害，并在Buff结束时额外受到一次伤害

首先创建一个Buff模板，规定它的持续时间为3秒，周期为1秒，我们让它每周期对Buff的所属单位造成30点伤害，并且在Buff完成时再造成一次额外伤害

![](/assets/images/持续伤害-a7cef3884dc5de6f0f3fb9f92cf46621.png)

具体效果：

![](/assets/images/持续伤害-4d54079b8c2a7340f3ae4eb35db7a6fa.gif)

可以看到单位每秒会受到30点伤害，并且会在Buff结束时受到10点额外的真实伤害

### 通过为单位添加Buff实现无敌[​](/Manual/GameMechanics/Buff#通过为单位添加buff实现无敌
"通过为单位添加Buff实现无敌的直接链接")

可以通过Buff与表现相结合的形式，将主控冰封住来实现无敌的效果：

首先创建标准Buff节点，在『属性最大值』中设置移动速度为0（用来实现定身效果）

![](/assets/images/冰棺-c3c81b9aa2ca377f5df54ba27cb75069.png)

然后在Buff右侧属性节点中进行配置（要勾选：显示高级属性）

  1. 禁用技能分类：可被禁用（我们希望单位被冰封状态下是无法使用可被禁用的技能的）
  2. 为单位添加状态：无敌、禁止转向（冰封状态下实现无敌，禁止转向则是为了让表现更加自然）

![](/assets/images/冰棺配置-640ed74272f8ad12786b350938f2fc56.png)

接下来我们来查看效果：

![](/assets/images/冰棺-6290a7c1df64939f6952c783e797ed86.gif)

此外，添加到主控单位的Buff还可以通过Buff列表显示在UI上，具体实现请参照[这篇文档](/Manual/UIEditor/Components/BuffList)。

**标签：**

  * [游戏机制](/tags/游戏机制)
  * [Buff](/tags/buff)

[上一页物品的配置](/Manual/GameMechanics/物品相关应用/物品的配置)[下一页交互行为](/Manual/GameMechanics/Interaction)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Buff

复制链接

# Buff

  * 类名：Buff

  * 方法：

    * [get_pulse():number](/技术文档/服务端TS API/Buff/方法/get_pulse)

    * [set_pulse(周期:number):void](/技术文档/服务端TS API/Buff/方法/set_pulse)

    * [get_remaining():number](/技术文档/服务端TS API/Buff/方法/get_remaining)

    * [set_remaining(剩余时长:number):void](/技术文档/服务端TS API/Buff/方法/set_remaining)

    * [get_time():number](/技术文档/服务端TS API/Buff/方法/get_time)

    * [set_time(总时长:number):void](/技术文档/服务端TS API/Buff/方法/set_time)

    * [get_stack():number](/技术文档/服务端TS API/Buff/方法/get_stack)

    * [add_stack_(层数:number):void](/技术��文档/服务端TS API/Buff/方法/add_stack_)

    * [set_stack_(层数:number):number](/技术文档/服务端TS API/Buff/方法/set_stack_)

    * [remove():void](/技术文档/服务端TS API/Buff/方法/remove)

    * [is_enabled():boolean](/技术文档/服务端TS API/Buff/方法/is_enabled)

    * [filter_categories(过滤器:Class:target_filters:1643118592):boolean](/技术文档/服务端TS API/Buff/方法/filter_categories)

    * [get_tracked_units():Class:UnitGroup1344536576](/技术文档/服务端TS API/Buff/方法/get_tracked_units)

    * [set_level(level:number):void](/技术文档/服务端TS API/Buff/方法/set_level)

    * [get_level():number](/技术文档/服务端TS API/Buff/方法/get_level)

    * [get_remain_time():number](/技术文档/服务端TS API/Buff/方法/get_remain_time)

    * [buff_get_tracked_units_v2():Class:UnitGroup1344536576](/技术文档/服务端TS API/Buff/方法/buff_get_tracked_units_v2)

    * [get_name():Preset:buff_id](/技术文档/服务端TS API/Buff/方法/get_name)

  * 属性：

    * [_cache_ (Class:_OBJ__buff_Buff)](/技术文档/服务端TS API/Buff/属性/cache)

    * [_link_ (Preset:buff_id)](/技术文档/服务端TS API/Buff/属性/link)

    * [_unit_buff_ (Class:UnitBuff:1181876224)](/技术文档/服务端TS API/Buff/属性/unit_buff)

    * [_stack_param_ (Class:EffectParam1160118272)](/技术文档/服务端TS API/Buff/属性/stack_param)

    * [_attributes_ (Class:Array)](/技术文档/服务端TS API/Buff/属性/attributes)

  * 相关页面：

    * 面向对象: [Buff](/技术文档/服务端面向对象 API/Buff/Buff)

[上一页finish](/技术文档/服务端TS API/AnimPointInfo/属性/finish)[下一页cache](/技术文档/服务端TS
API/Buff/属性/cache)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Buff

复制链接

# Buff

  * 类名：Buff

  * 方法：

    * [get_name():Preset:buff_id](/技术文档/客户端TS API/Buff/方法/get_name)

    * [get_show_name():string](/技术文档/客户端TS API/Buff/方法/get_show_name)

    * [get_icon():string](/技术文档/客户端TS API/Buff/方法/get_icon)

    * [get_tips():string](/技术文档/客户端TS API/Buff/方法/get_tips)

    * [get_current_cd():number](/技术文档/客户端TS API/Buff/方法/get_current_cd)

    * [get_cd_max():number](/技术文档/客户端TS API/Buff/方法/get_cd_max)

    * [get_remaining():number](/技术文档/客户端TS API/Buff/方法/get_remaining)

    * [get_time():number](/技术文档/客户端TS API/Buff/方法/get_time)

  * 属性：

    * [_cache_ (Class:_OBJ__buff_Buff)](/技术文档/客户端TS API/Buff/属性/cache)
  * 相关页面：

    * 面向对象: [Buff](/技术文档/客户端面向对象 API/Buff/Buff)

[上一页finish](/技术文档/客户端TS API/AnimPointInfo/属性/finish)[下一页cache](/技术文档/客户端TS
API/Buff/属性/cache)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端面向对象 API
  * Buff

复制链接

# Buff

  * 类名：Buff

  * 方法：

    * [获取周期():number](/技术文档/服务端面向对象 API/Buff/方法/获取周期)

    * [设置周期(周期:number):void](/技术文档/服务端面向对象 API/Buff/方法/设置周期)

    * [获取剩余时长():number](/技术文档/服务端面向对象 API/Buff/方法/获取剩余时长)

    * [设置剩余时长(剩余时长:number):void](/技术文档/服务端面向对象 API/Buff/方法/设置剩余时长)

    * [获取总时长():number](/技术文档/服务端面向对象 API/Buff/方法/获取总时长)

    * [设置总时长并重置剩余时长(总时长:number):void](/技术文档/服务端面向对象 API/Buff/方法/设置总时长并重置剩余时长)

    * [获取层数():number](/技术文档/服务端面向对象 API/Buff/方法/获取层数)

    * [增加层数(层数:number):void](/技术文档/服务端面向对象 API/Buff/方法/增加层数)

    * [设置层数(层数:number):number](/��技术文档/服务端面向对象 API/Buff/方法/设置层数)

    * [移除():void](/技术文档/服务端面向对象 API/Buff/方法/移除)

    * [是否启用():boolean](/技术文档/服务端面向对象 API/Buff/方法/是否启用)

    * [使用过滤器过滤的结果(过滤器:Class:target_filters:1643118592):boolean](/技术文档/服务端面向对象 API/Buff/方法/使用过滤器过滤的结果)

    * [获取Buff单位组的所有单位():Class:UnitGroup1344536576](/技术文档/服务端面向对象 API/Buff/方法/获取Buff单位组的所有单位)

    * [设置等级(新参数1:number):void](/技术文档/服务端面向对象 API/Buff/方法/设置等级)

    * [获取等级():number](/技术文档/服务端面向对象 API/Buff/方法/获取等级)

    * [获取剩余时长():number](/技术文档/服务端面向对象 API/Buff/方法/获取剩余时长)

    * [获取Buff单位组的所有单位():Class:UnitGroup1344536576](/技术文档/服务端面向对象 API/Buff/方法/获取Buff单位组的所有单位)

    * [获取数编Id():Preset:buff_id](/技术文档/服务端面向对象 API/Buff/方法/获取数编Id)

  * 属性：

    * [_数据表_ (Class:_OBJ__buff_Buff)](/技术文档/服务端面向对象 API/Buff/属性/数据表)

    * [_数编Id_ (Preset:buff_id)](/技术文档/服务端面向对象 API/Buff/属性/数编Id)

    * [_Buff管理器_ (Class:UnitBuff:1181876224)](/技术文档/服务端面向对象 API/Buff/属性/Buff管理器)

    * [_效果节点_ (Class:EffectParam1160118272)](/技术文档/服务端面向对象 API/Buff/属性/效果节点)

    * [_当前属性加成列表_ (Class:Array)](/技术文档/服务端面向对象 API/Buff/属性/当前属性加成列表)

  * 相关页面：

    * TS: [Buff](/技术文档/服务端TS API/Buff)

[上一页设置自定义仇恨函数](/技术文档/服务端面向对象 API/AI搜索器/方法/set_threat)[下一页数据表](/技术文档/服务端面向对象
API/Buff/属性/cache)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端面向对象 API
  * Buff

复制链接

# Buff

  * 类名：Buff

  * 方法：

    * [数编Id():Preset:buff_id](/技术文档/客户端面向对象 API/Buff/方法/数编Id)

    * [获取显示名():string](/技术文档/客户端面向对象 API/Buff/方法/获取显示名)

    * [获取图标():string](/技术文档/客户端面向对象 API/Buff/方法/获取图标)

    * [获取提示信息():string](/技术文档/客户端面向对象 API/Buff/方法/获取提示信息)

    * [获取冷却时间():number](/技术文档/客户端面向对象 API/Buff/方法/获取冷却时间)

    * [获取最大冷却时间():number](/技术文档/客户端面向对象 API/Buff/方法/获取最大冷却时间)

    * [获取显示用剩余冷却时间():number](/技术文档/客户端面向对象 API/Buff/方法/获取显示用剩余冷却时间)

    * [获取显示用最大冷却时间():number](/技术文档/客户端面向对象 API/Buff/方法/获取显示用最大冷却时间)

  * 属性：

    * [_数编表_ (Class:_OBJ__buff_Buff)](/技术文档/客户端面向对象 API/Buff/属性/数编表)
  * 相关页面：

    * TS: [Buff](/技术文档/客户端TS API/Buff)

[上一页创建飘浮文字并定义颜色和字号](/技术文档/客户端面向过程
API/默认/create_riseletter_with_color_size)[下一页数编表](/技术文档/客户端面向对象
API/Buff/属性/cache)


