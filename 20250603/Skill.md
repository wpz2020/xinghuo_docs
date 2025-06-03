  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Skill

复制链接

# Skill

  * 类名：Skill

  * 方法：

    * [active_cd(冷却上限:number,无视冷却缩减:boolean):void](/技术文档/服务端TS API/Skill/方法/active_cd)

    * [active_custom_cd(冷却上限:UnionType,当前冷却:number):void](/技术文档/服务端TS API/Skill/方法/active_custom_cd)

    * [add_level(等级:number):void](/技术文档/服务端TS API/Skill/方法/add_level)

    * [add_stack(层数:number):void](/技术文档/服务端TS API/Skill/方法/add_stack)

    * [get_num(数值属性:Preset:技能属性):number](/技术文档/服务端TS API/Skill/方法/get_num)

    * [set_num(数值属性:Preset:技能属性,值:number):void](/技术文档/服务端TS API/Skill/方法/set_num)

    * [get(技能属性:Preset:技能属性):any](/技术文档/服务端TS API/Skill/方法/get)

    * [set_option(技能属性:Preset:技能属性,值:any):void](/技术文档/服务端TS API/Skill/方法/set_option)

    * [disable():void](/技术文档/服务端TS API/Skill/方法/disable)

    * [enable():void](/技术文档/服务端TS API/Skill/方法/enable)

    * [enable_hidden():void](/技术文档/服务端TS API/Skill/方法/enable_hidden)

    * [disable_hidden():void](/技术文档/服务端TS API/Skill/方法/disable_hidden)

    * [get_cd():number](/技术文档/服务端TS API/Skill/方法/get_cd)

    * [get_level():number](/技术文档/服务端TS API/Skill/方法/get_level)

    * [get_name():Preset:spell_id](/技术文档/服务端TS API/Skill/方法/get_name)

    * [get_slot_id():number](/技术文档/服务端TS API/Skill/方法/get_slot_id)

    * [get_owner():Class:Unit](/技术文档/服务端TS API/Skill/方法/get_owner)

    * [get_type():[AbilSlotType](/技术文档/枚举文档/AbilSlotType)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Skill/方法/get_type)

    * [is_cast():boolean](/技术文档/服务端TS API/Skill/方法/is_cast)

    * [is_enable():boolean](/技术文档/服务端TS API/Skill/方法/is_enable)

    * [is_hidden():boolean](/技术文档/服务端TS API/Skill/方法/is_hidden)

    * [notify_damage(伤害:Class:DamageInstance1448869888):void](/技术文档/服务端TS API/Skill/方法/notify_damage)

    * [reload():void](/技术文档/服务端TS API/Skill/方法/reload)

    * [remove():void](/技术文档/服务端TS API/Skill/方法/remove)

    * [set_animation(动画:string):void](/技术文档/服务端TS API/Skill/方法/set_animation)

    * [set_cd(冷却:number):void](/技术文档/服务端TS API/Skill/方法/set_cd)

    * [set_cd_force(冷却:number,强制激活延长:boolean):void](/技术文档/服务端TS API/Skill/方法/set_cd_force)

    * [set_level(等级:number):void](/技术文档/服务端TS API/Skill/方法/set_level)

    * [set_upgradable(可升级:boolean):void](/技术文档/服务端TS API/Skill/方法/set_upgradable)

    * [event_notify(事件名称:string):void](/技术文档/服务端TS API/Skill/方法/event_notify)

    * [can_cast(target:UnionType,checkRange:boolean):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Skill/方法/can_cast)

    * [can_learn():boolean](/技术文档/服务端TS API/Skill/方法/can_learn)

    * [learn():boolean](/技术文档/服务端TS API/Skill/方法/learn)

    * [set_autocast_on(打开:boolean):void](/技术文档/服务端TS API/Skill/方法/set_autocast_on)

    * [get_active_item():Class:Item](/技术文档/服务端TS API/Skill/方法/get_active_item)

    * [get_disable_count():number](/技术文档/服务端TS API/Skill/方法/get_disable_count)

    * [set_phase(多段技能阶段:number):void](/技术文档/服务端TS API/Skill/方法/set_phase)

    * [is_toggled_on():boolean](/技术文档/服务端TS API/Skill/方法/is_toggled_on)

    * [ignore_pay_cd(是否关闭:boolean):void](/技术文档/服务端TS API/Skill/方法/ignore_pay_cd)

    * [get_stack():number](/技术文档/服务端TS API/Skill/方法/get_stack)

    * [get_skill_max_cd():number](/技术文档/服务端TS API/Skill/方法/get_skill_max_cd)

    * [get_multi_phase_max_cd(段数:number):number](/技术文档/服务端TS API/Skill/方法/get_multi_phase_max_cd)

  * 属性：

    * [_owner_ (Class:Unit)](/技术文档/服务端TS API/Skill/属性/owner)

    * [_cache_ (Class:_OBJ__spell_Spell)](/技术文档/服务端TS API/Skill/属性/cache)

    * [_last_target_ (UnionType)](/技术文档/服务端TS API/Skill/属性/last_target)

    * [_target_type_ (Preset:_OBJ__Spell_target_type)](/技术文档/服务端TS API/Skill/属性/target_type)

    * [_source_item_ (Class:Item)](/技术文档/服务端TS API/Skill/属性/source_item)

    * [_phase_ (number)](/技术文档/服务端TS API/Skill/属性/phase)

  * 相关页面：

    * 面向对象: [技能](/技术文档/服务端面向对象 API/技能/Skill)

[上一页Sight](/技术文档/服务端TS API/Sight/)[下一页owner](/技术文档/服务端TS API/Skill/属性/owner)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Skill

复制链接

# Skill

  * 类名：Skill

  * 方法：

    * [get_level():number](/技术文档/客户端TS API/Skill/方法/get_level)

    * [get_owner():Class:Unit](/技术文档/客户端TS API/Skill/方法/get_owner)

    * [get_name():Preset:spell_id](/技术文档/客户端TS API/Skill/方法/get_name)

    * [get_tip():string](/技术文档/客户端TS API/Skill/方法/get_tip)

    * [get_show_name():string](/技术文档/客户端TS API/Skill/方法/get_show_name)

    * [get_icon():string](/技术文档/客户端TS API/Skill/方法/get_icon)

    * [get_tips():string](/技术文档/客户端TS API/Skill/方法/get_tips)

    * [get_current_cd():number](/技术文档/客户端TS API/Skill/方法/get_current_cd)

    * [get_cd_max():number](/技术文档/客户端TS API/Skill/方法/get_cd_max)

    * [get_user_attribute(属性:string):any](/技术文档/客户端TS API/Skill/方法/get_user_attribute)

    * [is_toggled_on():boolean](/技术文档/客户端TS API/Skill/方法/is_toggled_on)

    * [get_phase():number](/技术文档/客户端TS API/Skill/方法/get_phase)

    * [get_current_show_cd():number](/技术文档/客户端TS API/Skill/方法/get_current_show_cd)

    * [get_max_show_cd():number](/技术文档/客户端TS API/Skill/方法/get_max_show_cd)

    * [get_currrent_charge_show_cd():number](/技术文档/客户端TS API/Skill/方法/get_currrent_charge_show_cd)

    * [get_max_charge_show_cd():number](/技术文档/客户端TS API/Skill/方法/get_max_charge_show_cd)

    * [get_current_charge_cd():number](/技术文档/客户端TS API/Skill/方法/get_current_charge_cd)

    * [get_charge_cd_max():number](/技术文档/客户端TS API/Skill/方法/get_charge_cd_max)

    * [get_stack():number](/技术文档/客户端TS API/Skill/方法/get_stack)

  * 属性：

    * [_cache_ (Class:_OBJ__spell_Spell)](/技术文档/客户端TS API/Skill/属性/cache)
  * 相关页面：

    * 面向对象: [技能](/技术文档/客户端面向对象 API/技能/Skill)

[上一页get_ui_y](/技术文档/客户端TS API/ScreenPos/方法/get_ui_y)[下一页cache](/技术文档/客户端TS
API/Skill/属性/cache)


