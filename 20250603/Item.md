  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Item

复制链接

# Item

  * 类名：Item

  * 方法：

    * [get_inv_index():number](/技术文档/服务端TS API/Item/方法/get_inv_index)

    * [get_slot():number](/技术文档/服务端TS API/Item/方法/get_slot)

    * [add_to(单位:Class:Unit):boolean](/技术文档/服务端TS API/Item/方法/add_to)

    * [add_extra_mod(buff_id:Preset:buff_id,是否装备:boolean):void](/技术文档/服务端TS API/Item/方法/add_extra_mod)

    * [remove_extra_mod(buff_id:Preset:buff_id,是否装备:boolean):void](/技术文档/服务端TS API/Item/方法/remove_extra_mod)

    * [generate_rand_mod(参考单位:Class:Unit):void](/技术文档/服务端TS API/Item/方法/generate_rand_mod)

    * [randomized_value(buff_id:Preset:buff_id,单位属性:Preset:单位属性,百分比:boolean,编号:number):number](/技术文档/服务端TS API/Item/方法/randomized_value)

    * [set_stack(层数:number):void](/技术文档/服务端TS API/Item/方法/set_stack)

    * [get_stack():number](/技术文档/服务端TS API/Item/方法/get_stack)

    * [get_unit():Class:Unit](/技术文档/服务端TS API/Item/方法/get_unit)

    * [carrier():Class:Unit](/技术文档/服务端TS API/Item/方法/carrier)

    * [id():Preset:item_id](/技术文档/服务端TS API/Item/方法/id)

    * [remove():void](/技术文档/服务端TS API/Item/方法/remove)

    * [drop():boolean](/技术文档/服务端TS API/Item/方法/drop)

    * [get_active_skill():Class:Skill](/技术文档/服务端TS API/Item/方法/get_active_skill)

    * [get_item_info():Class:LuaTable](/技术文档/服务端TS API/Item/方法/get_item_info)

    * [get_inventory():Class:Inventory2214723584.0](/技术文档/服务端TS API/Item/方法/get_inventory)

    * [set_quality(品质:number):void](/技术文档/服务端TS API/Item/方法/set_quality)

    * [get_quality():number](/技术文档/服务端TS API/Item/方法/get_quality)

    * [add_extra_attr(属性:Preset:单位属性,数值:number,类型:Preset:单位属性子类型,装备属性:boolean):void](/技术文档/服务端TS API/Item/方法/add_extra_attr)

    * [foreach_extra_attr(对每个额外属性:FuncType):void](/技术文档/服务端TS API/Item/方法/foreach_extra_attr)

    * [cleat_extra_attr_all():void](/技术文档/服务端TS API/Item/方法/cleat_extra_attr_all)

    * [cleat_extra_attr(属性:Preset:单位属性,属性类型:Preset:单位属性子类型,是装备属性:boolean):void](/技术文档/服务端TS API/Item/方法/cleat_extra_attr)

    * [add_attr_need(属性:Preset:单位属性,数值:number):void](/技术文档/服务端TS API/Item/方法/add_attr_need)

    * [remove_attr_need(属性:Preset:单位属性):void](/技术文档/服务端TS API/Item/方法/remove_attr_need)

    * [foreach_attr_need(对每个物品需求:FuncType):void](/技术文档/服务端TS API/Item/方法/foreach_attr_need)

    * [bind_to_user(玩家:Class:Player,绑定成功时:FuncType,绑定失败时:FuncType):void](/技术文档/服务端TS API/Item/方法/bind_to_user)

    * [unbind_to_user(解绑成功时:FuncType,解绑失败时:FuncType):void](/技术文档/服务端TS API/Item/方法/unbind_to_user)

    * [update_score_money(更新成功时:FuncType,更新失败时:FuncType):void](/技术文档/服务端TS API/Item/方法/update_score_money)

    * [score_use(数量:number,消耗成功时:FuncType,消耗失败时:FuncType):void](/技术文档/服务端TS API/Item/方法/score_use)

    * [get_all_extra_mod(是否装备:IsEquipped):Class:Array](/技术文档/服务端TS API/Item/方法/get_all_extra_mod)

    * [set_score_custom_data(数据:Class:LuaTable):void](/技术文档/服务端TS API/Item/方法/set_score_custom_data)

    * [get_score_custom_data():Class:LuaTable](/技术文档/服务端TS API/Item/方法/get_score_custom_data)

    * [get_name():Preset:item_id](/技术文档/服务端TS API/Item/方法/get_name)

    * [get_bind_user():Class:用户id:3023175680](/技术文档/服务端TS API/Item/方法/get_bind_user)

    * [can_use(target:UnionType,checkRange:boolean):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Item/方法/can_use)

  * 属性：

    * [_inv_index_ (number)](/技术文档/服务端TS API/Item/属性/inv_index)

    * [_slot_ (Class:Slot2407792640.0)](/技术文档/服务端TS API/Item/属性/slot)

    * [_stack_ (number)](/技术文档/服务端TS API/Item/属性/stack)

    * [_unit_ (Class:Unit)](/技术文档/服务端TS API/Item/属性/unit)

    * [_link_ (Preset:item_id)](/技术文档/服务端TS API/Item/属性/link)

    * [_active_skill_ (Class:Skill)](/技术文档/服务端TS API/Item/属性/active_skill)

    * [_cache_ (Class:_OBJ__item_Item)](/技术文档/服务端TS API/Item/属性/cache)

    * [_granted_tag_ (string)](/技术文档/服务端TS API/Item/属性/granted_tag)

    * [_removed_ (boolean)](/技术文档/服务端TS API/Item/属性/removed)

  * 相关页面：

    * 面向对象: [物品](/技术文档/服务端面向对象 API/物品/Item)

[上一页set_state](/技术文档/服务端TS
API/Inventory/方法/set_state)[下一页inv_index](/技术文档/服务端TS API/Item/属性/inv_index)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Item

复制链接

# Item

  * 类名：Item

  * 方法：

    * [foreach_extra_attr(对每个额外属性:FuncType):void](/技术文档/客户端TS API/Item/方法/foreach_extra_attr)

    * [foreach_attr_need(对每个物品需求:FuncType):void](/技术文档/客户端TS API/Item/方法/foreach_attr_need)

    * [get_item_quality():number](/技术文档/客户端TS API/Item/方法/get_item_quality)

    * [get_item_quality_color():string](/技术文档/客户端TS API/Item/方法/get_item_quality_color)

    * [get_item_quality_frame():string](/技术文档/客户端TS API/Item/方法/get_item_quality_frame)

    * [get_item_quality_title():string](/技术文档/客户端TS API/Item/方法/get_item_quality_title)

    * [get_all_extra_mod(是否装备:IsEquipped):Class:Array](/技术文档/客户端TS API/Item/方法/get_all_extra_mod)

    * [get_show_name():string](/技术文档/客户端TS API/Item/方法/get_show_name)

    * [get_icon():string](/技术文档/客户端TS API/Item/方法/get_icon)

    * [get_tips():string](/技术文档/客户端TS API/Item/方法/get_tips)

    * [get_current_cd():number](/技术文档/客户端TS API/Item/方法/get_current_cd)

    * [get_cd_max():number](/技术文档/客户端TS API/Item/方法/get_cd_max)

    * [get_name():Preset:item_id](/技术文档/客户端TS API/Item/方法/get_name)

    * [get_rand_mod(buff_id:Preset:buff_id,buff下标:number,属性名:Preset:单位属性,子属性类型:Preset:单位属性子类型):number](/技术文档/客户端TS API/Item/方法/get_rand_mod)

    * [get_stack():number](/技术文档/客户端TS API/Item/方法/get_stack)

  * 属性：

    * [_unit_ (Class:Unit)](/技术文档/客户端TS API/Item/属性/unit)

    * [_inv_index_ (number)](/技术文档/客户端TS API/Item/属性/inv_index)

    * [_slot_index_ (number)](/技术文档/客户端TS API/Item/属性/slot_index)

    * [_cache_ (Class:_OBJ__item_Item)](/技术文档/客户端TS API/Item/属性/cache)

  * 相关页面：

    * 面向对象: [物品](/技术文档/客户端面向对象 API/物品/Item)

[上一页one_more_round](/技术文档/客户端TS
API/Game/方法/one_more_round)[下一页unit](/技术文档/客户端TS API/Item/属性/unit)


