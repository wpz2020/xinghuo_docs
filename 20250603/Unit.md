  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Unit

复制链接

# Unit

  * 类名：Unit

  * 方法：

    * [attack(目标:Class:Unit):void](/技术文档/服务端TS API/Unit/方法/attack)

    * [add(单位属性:Preset:单位属性,数值:number):void](/技术文档/服务端TS API/Unit/方法/add)

    * [attack_skill():UnionType](/技术文档/服务端TS API/Unit/方法/attack_skill)

    * [get_id():number](/技术文档/服务端TS API/Unit/方法/get_id)

    * [enable_ai():void](/技术文档/服务端TS API/Unit/方法/enable_ai)

    * [add_skill(技能名称:Preset:spell_id,技能类型:AbilSlotType,技能格子:number):void](/技术文档/服务端TS API/Unit/方法/add_skill)

    * [blink_ex(目标点:Class:Point):boolean](/技术文档/服务端TS API/Unit/方法/blink_ex)

    * [create_item(物品名称:Preset:item_id,创建位置:UnionType):Class:Item](/技术文档/服务端TS API/Unit/方法/create_item)

    * [can_attack(目标:Class:Unit):boolean](/技术文档/服务端TS API/Unit/方法/can_attack)

    * [disable_ai():void](/技术文档/服务端TS API/Unit/方法/disable_ai)

    * [set_loot(掉落列表Id:Preset:loot_id):void](/技术文档/服务端TS API/Unit/方法/set_loot)

    * [add_ex(单位数值属性:Preset:单位属性,变化值:number,单位数值属性类型:UnitPropertySubType):void](/技术文档/服务端TS API/Unit/方法/add_ex)

    * [add_height(高度:number):void](/技术文档/服务端TS API/Unit/方法/add_height)

    * [add_resource(能量类型:string,值:number):void](/技术文档/服务端TS API/Unit/方法/add_resource)

    * [add_restriction(单位标记:Preset:_OBJ__Unit_Restriction):void](/技术文档/服务端TS API/Unit/方法/add_restriction)

    * [add_sight(可见形状:Class:Sight4095868928.0):void](/技术文档/服务端TS API/Unit/方法/add_sight)

    * [get_ex(单位数值属性:Preset:单位属性,单位数值属性类型:UnitPropertySubType):number](/技术文档/服务端TS API/Unit/方法/get_ex)

    * [get_attribute_max(单位数值属性:Preset:单位属性):number](/技术文档/服务端TS API/Unit/方法/get_attribute_max)

    * [get_attribute_min(单位数值属性:Preset:单位属性):number](/技术文档/服务端TS API/Unit/方法/get_attribute_min)

    * [get_class():Preset:_OBJ__UnitData_UnitClass](/技术文档/服务端TS API/Unit/方法/get_class)

    * [get_facing():number](/技术文档/服务端TS API/Unit/方法/get_facing)

    * [get_height():number](/技术文档/服务端TS API/Unit/方法/get_height)

    * [get_name():Preset:unit_id](/技术文档/服务端TS API/Unit/方法/get_name)

    * [get_owner():Class:Player](/技术文档/服务端TS API/Unit/方法/get_owner)

    * [get_scene_point():Class:Point](/技术文档/服务端TS API/Unit/方法/get_scene_point)

    * [get_resource(能量类型:string):number](/技术文档/服务端TS API/Unit/方法/get_resource)

    * [get_restriction(单位标记:UnitBehaviorState):number](/技术文档/服务端TS API/Unit/方法/get_restriction)

    * [get_attackable_radius():number](/技术文档/服务端TS API/Unit/方法/get_attackable_radius)

    * [get_team_id():number](/技术文档/服务端TS API/Unit/方法/get_team_id)

    * [walk(目标点:Class:Point):[WalkResultCode](/技术文档/枚举文档/WalkResultCode)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/walk)

    * [has_restriction(单位标记:UnitBehaviorState):boolean](/技术文档/服务端TS API/Unit/方法/has_restriction)

    * [is_alive_ex():boolean](/技术文档/服务端TS API/Unit/方法/is_alive_ex)

    * [is_ally(目标:UnionType):boolean](/技术文档/服务端TS API/Unit/方法/is_ally)

    * [is_enemy(目标:UnionType):boolean](/技术文档/服务端TS API/Unit/方��法/is_enemy)

    * [is_illusion():boolean](/技术文档/服务端TS API/Unit/方法/is_illusion)

    * [is_in_range(目标:UnionType,范围半径:number):boolean](/技术文档/服务端TS API/Unit/方法/is_in_range)

    * [is_visible(目标:UnionType):boolean](/技术文档/服务端TS API/Unit/方法/is_visible)

    * [is_walking():boolean](/技术文档/服务端TS API/Unit/方法/is_walking)

    * [add_z_speed(速度:number):void](/技术文档/服务端TS API/Unit/方法/add_z_speed)

    * [set_z_speed():void](/技术文档/服务端TS API/Unit/方法/set_z_speed)

    * [get_z_speed():number](/技术文档/服务端TS API/Unit/方法/get_z_speed)

    * [kill(凶手:Class:Unit):void](/技术文档/服务端TS API/Unit/方法/kill)

    * [learn_skill(技能:UnionType):boolean](/技术文档/服务端TS API/Unit/方法/learn_skill)

    * [reborn(位置:Class:Point):void](/技术文档/服务端TS API/Unit/方法/reborn)

    * [remove():void](/技术文档/服务端TS API/Unit/方法/remove)

    * [remove_buff(BuffId:Preset:buff_id):void](/技术文档/服务端TS API/Unit/方法/remove_buff)

    * [remove_provide_sight(队伍编号:number):void](/技术文档/服务端TS API/Unit/方法/remove_provide_sight)

    * [remove_restriction(单位标记:Preset:_OBJ__Unit_Restriction):void](/技术文档/服务端TS API/Unit/方法/remove_restriction)

    * [replace_skill(旧技能Id:Preset:spell_id,新技能Id:Preset:spell_id):void](/技术��文档/服务端TS API/Unit/方法/replace_skill)

    * [set_ex(单位数值属性:Preset:单位属性,值:number,单位数值属性类型:UnitPropertySubType):void](/技术文档/服务端TS API/Unit/方法/set_ex)

    * [get(单位属性:UnionType):any](/技术文档/服务端TS API/Unit/方法/get)

    * [set(单位属性:UnionType,值:any):void](/技术文档/服务端TS API/Unit/方法/set)

    * [set_attribute_max(单位数值属性:Preset:单位属性,上限:number):void](/技术文档/服务端TS API/Unit/方法/set_attribute_max)

    * [set_attribute_min(单位数值属性:Preset:单位属性,下限:number):void](/技术文档/服务端TS API/Unit/方法/set_attribute_min)

    * [set_attribute_sync(单位属性:UnionType,同步方式:SyncType):void](/技术文档/服务端TS API/Unit/方法/set_attribute_sync)

    * [set_facing(角度:number):void](/技术文档/服务端TS API/Unit/方法/set_facing)

    * [set_height(高度:number):void](/技术文档/服务端TS API/Unit/方法/set_height)

    * [set_asset(模型:Preset:model_id):void](/技术文档/服务端TS API/Unit/方法/set_asset)

    * [set_resource(能量类型:string,值:number):void](/技术文档/服务端TS API/Unit/方法/set_resource)

    * [set_attackable_radius(选取半径:number):void](/技术文档/服务端TS API/Unit/方法/set_attackable_radius)

    * [get_scene_name():Preset:Scene](/技术文档/服务端TS API/Unit/方法/get_scene_name)

    * [jump_scene(场景:Preset:Scene):boolean](/技术文档/服务端TS API/Unit/方法/jump_scene)

    * [set_location_async(位置:Class:Point):void](/技术文档/服务端TS API/Unit/方法/set_location_async)

    * [set_facing_async(朝向:number):void](/技术文档/服务端TS API/Unit/方法/set_facing_async)

    * [get_exp():number](/技术文档/服务端TS API/Unit/方法/get_exp)

    * [add_exp(经验值:number,是否忽略倍率:boolean):void](/技术文档/服务端TS API/Unit/方法/add_exp)

    * [set_exp(经验值:number):void](/技术文档/服务端TS API/Unit/方法/set_exp)

    * [get_level():number](/技术文档/服务端TS API/Unit/方法/get_level)

    * [add_level(等级:number):void](/技术文档/服务端TS API/Unit/方法/add_level)

    * [set_level(等级:number):void](/技术文档/服务端TS API/Unit/方法/set_level)

    * [get_max_level():number](/技术文档/服务端TS API/Unit/方法/get_max_level)

    * [set_max_level(等级上限:number):void](/技术文档/服务端TS API/Unit/方法/set_max_level)

    * [get_exp_fraction():number](/技术文档/服务端TS API/Unit/方法/get_exp_fraction)

    * [set_exp_fraction(经验倍率:number):void](/技术文档/服务端TS API/Unit/方法/set_exp_fraction)

    * [set_prohibit_exp_distribute(是否禁止参与:boolean):void](/技术文档/服务端TS API/Unit/方法/set_prohibit_exp_distribute)

    * [set_level_profile(单位升级配置Id:Preset:unit_level_profile_id):undefined](/技术文档/服务端TS API/Unit/方法/set_level_profile)

    * [get_single_level_exp(等级:number):number](/技术文档/服务端TS API/Unit/方法/get_single_level_exp)

    * [get_cumu_level_exp(等级:number):number](/技术文档/服务端TS API/Unit/方法/get_cumu_level_exp)

    * [cast(技能:UnionType,目标:UnionType):void](/技术文档/服务端TS API/Unit/方法/cast)

    * [cast_no_target(技能:UnionType):void](/技术文档/服务端TS API/Unit/方法/cast_no_target)

    * [cast_on_unit(技能:UnionType,目标单位:Class:Unit):void](/技术文档/服务端TS API/Unit/方法/cast_on_unit)

    * [cast_on_point(技能:UnionType,目标点:Class:Point):void](/技术文档/服务端TS API/Unit/方法/cast_on_point)

    * [cast_on_angle(技能:UnionType,目标角度:number):void](/技术文档/服务端TS API/Unit/方法/cast_on_angle)

    * [clean_command():void](/技术文档/服务端TS API/Unit/方法/clean_command)

    * [current_skill():Class:Cast](/技术文档/服务端TS API/Unit/方法/current_skill)

    * [add_provide_sight(队伍Id:number):void](/技术文档/服务端TS API/Unit/方法/add_provide_sight)

    * [get_snapshot():Class:Snapshot3383230464.0](/技术文档/服务端TS API/Unit/方法/get_snapshot)

    * [create_inventorys():void](/技术文档/服务端TS API/Unit/方法/create_inventorys)

    * [create_inventory(数编id:Preset:item_container_id):Class:Inventory2214723584.0](/技术文档/服务端TS API/Unit/方法/create_inventory)

    * [can_hold(物品:Class:Item):boolean](/技术文档/服务端TS API/Unit/方法/can_hold)

    * [execute_on(目标:UnionType,效果名:Preset:effect_id):Preset:验证器代码4224974848.0](/技术文档/服务端TS API/Unit/方法/execute_on)

    * [has_item(物品id:Preset:item_id):boolean](/技术文档/服务端TS API/Unit/方法/has_item)

    * [all_items():Class:Array](/技术文档/服务端TS API/Unit/方法/all_items)

    * [do_trigger_damage(目标单位:Class:Unit,伤害:number,伤害类型:Preset:伤害类型):void](/技术文档/服务端TS API/Unit/方法/do_trigger_damage)

    * [find_buff(BuffId:Preset:buff_id):UnionType](/技术文档/服务端TS API/Unit/方法/find_buff)

    * [has_buff(id:Preset:buff_id):boolean](/技术文档/服务端TS API/Unit/方法/has_buff)

    * [find_skill(技能Id:Preset:spell_id):UnionType](/技术文档/服务端TS API/Unit/方法/find_skill)

    * [heal_ex(目标:Class:Unit,治疗量:number):void](/技术文档/服务端TS API/Unit/方法/heal_ex)

    * [remove_animation(动画名称:string):void](/技术文档/服务端TS API/Unit/方法/remove_animation)

    * [each_skill(技能类型:AbilSlotType):void](/技术文档/服务端TS API/Unit/方法/each_skill)

    * [each_mover():Class:Array](/技术文档/服务端TS API/Unit/方法/each_mover)

    * [each_buff(buff_id:Preset:buff_id):Class:Array](/技术文档/服务端TS API/Unit/方法/each_buff)

    * [get_buff_stack_all(BuffId:Preset:buff_id):number](/技术文档/服务端TS API/Unit/方法/get_buff_stack_all)

    * [each_skill_all():Class:Array](/技术文档/服务端TS API/Unit/方法/each_skill_all)

    * [set_model_attribute(模型属性:string,值:any):void](/技术文档/服务端TS API/Unit/方法/set_model_attribute)

    * [execute_ai():void](/技术文档/服务端TS API/Unit/方法/execute_ai)

    * [event_notify(事件名:string):void](/技术文档/服务端TS API/Unit/方法/event_notify)

    * [grant_loot(奖励Id:Preset:loot_id,目标单位:Class:Unit):void](/技术文档/服务端TS API/Unit/方法/grant_loot)

    * [change_type(unitId:Preset:unit_id):boolean](/技术文档/服务端TS API/Unit/方法/change_type)

    * [refresh_unit_buff_actors():void](/技术文档/服务端TS API/Unit/方法/refresh_unit_buff_actors)

    * [find_skill_by_slot(slot:number):UnionType](/技术文档/服务端TS API/Unit/方法/find_skill_by_slot)

    * [set_owner(player:Class:Player):void](/技术文档/服务端TS API/Unit/方法/set_owner)

    * [get_attack():Class:Skill](/技术文档/服务端TS API/Unit/方法/get_attack)

    * [has_module(组件:Preset:_OBJ__UnitData_Module):boolean](/技术文档/服务端TS API/Unit/方法/has_module)

    * [is_item():boolean](/技术文档/服务端TS API/Unit/方法/is_item)

    * [set_scale(缩放:number):void](/技术文档/服务端TS API/Unit/方法/set_scale)

    * [has_label(filter:Preset:单位标签):boolean](/技术文档/服务端TS API/Unit/方法/has_label)

    * [has_immunity(flag:UnitBehaviorState):boolean](/技术文档/服务端TS API/Unit/方法/has_immunity)

    * [get_inventory_items(物品栏编号:number):Class:Array](/技术文档/服务端TS API/Unit/方法/get_inventory_items)

    * [is_valid():boolean](/技术文档/服务端TS API/Unit/方法/is_valid)

    * [set_custom(属性:Preset:单位属性,子属性:Preset:单位属性子类型,值:number):void](/技术文档/服务端TS API/Unit/方法/set_custom)

    * [add_custom(属性:Preset:单位属性,子属性:Preset:单位属性子类型,变化值:number):void](/技术文档/服务端TS API/Unit/方法/add_custom)

    * [get_custom(属性:Preset:单位属性,子属性:Preset:单位属性子类型):number](/技术文档/服务端TS API/Unit/方法/get_custom)

    * [get_buffs_by_link(BuffId:Preset:buff_id):Class:Array](/技术文档/服务端TS API/Unit/方法/get_buffs_by_link)

    * [add_buff(link:string):FuncType](/技术文档/服务端TS API/Unit/方法/add_buff)

    * [assign_item_to_slot_by_id(物品:Class:Item,格子ID:number):boolean](/技术文档/服务端TS API/Unit/方法/assign_item_to_slot_by_id)

    * [has_ai():boolean](/技术文档/服务端TS API/Unit/方法/has_ai)

    * [set_string(单位属性:Preset:单位字符串属性,值:string):void](/技术文档/服务端TS API/Unit/方法/set_string)

    * [get_string(单位属性:Preset:单位字符串属性):string](/技术文档/服务端TS API/Unit/方法/get_string)

    * [refresh(新参数:Preset:单位属性):void](/技术文档/服务端TS API/Unit/方法/refresh)

    * [anim_play(动画名:string,时间因子:number,时间因子类型:number,从动画的第x秒播放:number,动画优先级:number):void](/技术文档/服务端TS API/Unit/方法/anim_play)

    * [anim_play_bracket(出生动画:string,持续动画:string,结束动画:string):void](/技术文档/服务端TS API/Unit/方法/anim_play_bracket)

    * [anim_play_once(动画名:string,动画优先级:number):void](/技术文档/服务端TS API/Unit/方法/anim_play_once)

    * [anim_play_speed(动画名:string,播放速度:number,动画优先级:number):void](/技术文档/服务端TS API/Unit/方法/anim_play_speed)

    * [anim_play_time(动画名:string,持续时间:number,动画优先级:number):void](/技术文档/服务端TS API/Unit/方法/anim_play_time)

    * [anim_play_start_time(动画名:string,开始时间:number,速度:number,动画优先级:number):void](/技术文档/服务端TS API/Unit/方法/anim_play_start_time)

    * [anim_play_bracket_once(出生动画:string,持续动画:string,结束动画:string):void](/技术文档/服务端TS API/Unit/方法/anim_play_bracket_once)

    * [anim_play_bracket_time(出生动画:string,持续动画:string,结束动画:string,持续时间:number):void](/技术文档/服务端TS API/Unit/方法/anim_play_bracket_time)

    * [anim_stop():void](/技术文档/服务端TS API/Unit/方法/anim_stop)

    * [cast_on_switch(技能:UnionType,开关状态:boolean):void](/技术文档/服务端TS API/Unit/方法/cast_on_switch)

    * [remove_inventory(物品栏:Class:Inventory2214723584.0):void](/技术文档/服务端TS API/Unit/方法/remove_inventory)

    * [cast_request(skill:UnionType,target:UnionType,data:Class:LuaTable):void](/技术文档/服务端TS API/Unit/方法/cast_request)

    * [stop():void](/技术文档/服务端TS API/Unit/方法/stop)

    * [receive_quest(任务Id:Preset:quest_id):Class:任务:617009083](/技术文档/服务端TS API/Unit/方法/receive_quest)

    * [get_quests():Class:Array](/技术文档/服务端TS API/Unit/方法/get_quests)

    * [get_quest_conditions():Class:Array](/技术文档/服务端TS API/Unit/方法/get_quest_conditions)

    * [set_attribute_max_user(属性:Preset:单位属性,最大值:number):void](/技术文档/服务端TS API/Unit/方法/set_attribute_max_user)

    * [get_walking_target():Class:Point](/技术文档/服务端TS API/Unit/方法/get_walking_target)

    * [find_quest(quest_link:Preset:quest_id):Class:任务:617009083](/技术文档/服务端TS API/Unit/方法/find_quest)

    * [set_visible(玩家:Class:Player,可见性:Preset:PVisibilitySetting:2772010051):void](/技术文档/服务端TS API/Unit/方法/set_visible)

    * [find_skill_by_id(技能Id:Preset:spell_id,是否包括0级技能:boolean):UnionType](/技术文档/服务端TS API/Unit/方法/find_skill_by_id)

    * [get_inventory(物品栏编号:number):Class:Inventory2214723584.0](/技术文档/服务端TS API/Unit/方法/get_inventory)

    * [set_scale_xyz(X轴缩放:number,Y轴缩放:number,Z轴缩放:number):void](/技术文档/服务端TS API/Unit/方法/set_scale_xyz)

    * [behavior_action(目标单位:Class:Unit,技能:Preset:spell_id):void](/技术文档/服务端TS API/Unit/方法/behavior_action)

    * [behavior_action_by(目标单位:Class:Unit,技能:Preset:spell_id):void](/技术文档/服务端TS API/Unit/方法/behavior_action_by)

    * [get_walk_path_points():Class:Array](/技术文档/服务端TS API/Unit/方法/get_walk_path_points)

    * [reset_ai_to(AI名称:UnionType,参数:UnionType):void](/技术文档/服务端TS API/Unit/方法/reset_ai_to)

    * [get_cooldown(冷却组:string):number](/技术文档/服务端TS API/Unit/方法/get_cooldown)

    * [set_cooldown(冷却组:string,冷却时间:number):void](/技术文档/服务端TS API/Unit/方法/set_cooldown)

    * [get_creation_param():Class:EffectParam1160118272](/技术文档/服务端TS API/Unit/方法/get_creation_param)

    * [move_to_direction_request(X轴参数:number,Y轴参数:number):void](/技术文档/服务端TS API/Unit/方法/move_to_direction_request)

    * [stop_move_to_direction_request():void](/技术文档/服务端TS API/Unit/方法/stop_move_to_direction_request)

    * [texttag_by_location(目标单位:Class:Unit,位置:UnionType,同步方式:SyncType,文字内容:string,漂浮文字类型:Preset:riseletter_id):void](/技术文档/服务端TS API/Unit/方法/texttag_by_location)

    * [texttag_by_location_color_size(目标单位:Class:Unit,位置:UnionType,同步方式:SyncType,文字内容:string,漂浮文字类型:Preset:riseletter_id,RGB和字号:Class:Array):void](/技术文档/服务端TS API/Unit/方法/texttag_by_location_color_size)

    * [attach_to(目标单位:Class:Unit,绑点:string):void](/技术文档/服务端TS API/Unit/方法/attach_to)

    * [ride_on(目标单位:Class:Unit,绑点:string,骑乘动画:string):void](/技术文档/服务端TS API/Unit/方法/ride_on)

    * [approach(目标:UnionType,最大距离:number,最小距离:number):void](/技术文档/服务端TS API/Unit/方法/approach)

    * [clean_recast():void](/技术文档/服务端TS API/Unit/方法/clean_recast)

    * [has_restriction_custom(单位标记:Preset:单位状态):boolean](/技术文档/服务端TS API/Unit/方法/has_restriction_custom)

    * [get_restriction_custom(单位标记:Preset:单位状态):number](/技术文档/服务端TS API/Unit/方法/get_restriction_custom)

    * [walk_to_unit(目标单位:Class:Unit):[WalkResultCode](/技术文档/枚举文档/WalkResultCode)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/walk_to_unit)

    * [set_status_bar_visibility(可见性:boolean):void](/技术文档/服务端TS API/Unit/方法/set_status_bar_visibility)

    * [create_item_param(物品:Class:Item,创建单位:Class:Unit):Class:EffectParam1160118272](/技术文档/服务端TS API/Unit/方法/create_item_param)

    * [use_item_no_target(物品:Class:Item):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/use_item_no_target)

    * [use_item_on_point(物品:Class:Item,目标点:Class:Point):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/use_item_on_point)

    * [use_item_on_unit(物品:Class:Item,目标单位:Class:Unit):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/use_item_on_unit)

    * [use_item_on_angle(物品:Class:Item,目标角度:number):[cast_error_code](/技术文档/枚举文档/cast_error_code)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Unit/方法/use_item_on_angle)

  * 属性：

    * [_cache_ (Class:_OBJ__unit_Unit)](/技术文档/服务端TS API/Unit/属性/cache)

    * [_inventorys_ (Class:Array)](/技术文档/服务端TS API/Unit/属性/inventorys)

    * [_ai_ (Class:AI:2542010368)](/技术文档/服务端TS API/Unit/属性/ai)

    * [_removed_ (boolean)](/技术文档/服务端TS API/Unit/属性/removed)

  * 相关页面：

    * 面向对象: [单位](/技术文档/服务端面向对象 API/单位/Unit)

[上一页TriggerParamTable](/技术文档/服务端TS
API/TriggerParamTable/)[下一页cache](/技术文档/服务端TS API/Unit/属性/cache)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Unit

复制链接

# Unit

  * 类名：Unit

  * 继承：[目标](/技术文档/客户端TS API/目标)

  * 方法：

    * [find_skill(技能id:Preset:spell_id,是否:boolean):Class:Skill](/技术文档/客户端TS API/Unit/方法/find_skill)

    * [get(数值属性:Preset:单位属性):number](/技术文档/客户端TS API/Unit/方法/get)

    * [get_name():Preset:unit_id](/技术文档/客户端TS API/Unit/方法/get_name)

    * [event_notify(事件名称:string):void](/技术文档/客户端TS API/Unit/方法/event_notify)

    * [get_level():number](/技术文档/客户端TS API/Unit/方法/get_level)

    * [get_tag():Preset:单位标签](/技术文档/客户端TS API/Unit/方法/get_tag)

    * [find_skill_by_slot(slot:number):UnionType](/技术文档/客户端TS API/Unit/方法/find_skill_by_slot)

    * [execute_on(target:Class:Target:589955072,link:UnionType):Preset:验证器代码4224974848.0](/技术文档/客户端TS API/Unit/方法/execute_on)

    * [get_all_items():Class:Array](/技术文档/客户端TS API/Unit/方法/get_all_items)

    * [is_item():boolean](/技术文档/客户端TS API/Unit/方法/is_item)

    * [find_buff(buff_id:Preset:buff_id):Class:Buff](/技术文档/客户端TS API/Unit/方法/find_buff)

    * [get_point():Class:Point](/技术文档/客户端TS API/Unit/方法/get_point)

    * [get_socket_position(绑点:string):Class:Point](/技术文档/客户端TS API/Unit/方法/get_socket_position)

    * [attach_to(目标:UnionType,绑点:string):void](/技术文档/客户端TS API/Unit/方法/attach_to)

    * [get_facing():number](/技术文档/客户端TS API/Unit/方法/get_facing)

    * [get_socket_rotation(绑点:string):Class:XYZ旋转:1136001024](/技术文档/客户端TS API/Unit/方法/get_socket_rotation)

    * [set_rotation(X轴:number,Y轴:number,Z轴:number):void](/技术文档/客户端TS API/Unit/方法/set_rotation)

    * [get_string(字符串属性:Preset:单位字符串属性):string](/技术文档/客户端TS API/Unit/方法/get_string)

    * [get_display_name():string](/技术文档/客户端TS API/Unit/方法/get_display_name)

    * [set_display_name(显示名:string):void](/技术文档/客户端TS API/Unit/方法/set_display_name)

    * [get_inventory_items(inv_idx:number):Class:Array](/技术文档/客户端TS API/Unit/方法/get_inventory_items)

    * [each_skill_all():Class:Array](/技术文档/客户端TS API/Unit/方法/each_skill_all)

    * [set_blood_bar_template(模版:Preset:bloodstrip_id):void](/技术文档/客户端TS API/Unit/方法/set_blood_bar_template)

    * [get_show_name():string](/技术文档/客户端TS API/Unit/方法/get_show_name)

    * [get_tips():string](/技术文档/客户端TS API/Unit/方法/get_tips)

    * [get_icon():string](/技术文档/客户端TS API/Unit/方法/get_icon)

    * [get_current_cd():number](/技术文档/客户端TS API/Unit/方法/get_current_cd)

    * [get_cd_max():number](/技术文档/客户端TS API/Unit/方法/get_cd_max)

    * [get_attack():Class:Skill](/技术文档/客户端TS API/Unit/方法/get_attack)

    * [set_minimap_icon_visible(是否显示:boolean):void](/技术文档/客户端TS API/Unit/方法/set_minimap_icon_visible)

    * [get_cooldown(冷却组:string):number](/技术文档/客户端TS API/Unit/方法/get_cooldown)

    * [create_riseletter_by_link(位置:Class:ScreenPos:3086221312,文本:string,类型:Preset:riseletter_id,颜色:string,字号:number):Class:Riseletter:3095523417](/技术文档/客户端TS API/Unit/方法/create_riseletter_by_link)

    * [create_riseletter_by_templatename(位置:Class:ScreenPos:3086221312,文本:string,模板名:string,颜色:string,字号:number):Class:Riseletter:3095523417](/技术文档/客户端TS API/Unit/方法/create_riseletter_by_templatename)

    * [remove_riseletter(飘字:Class:Riseletter:3095523417):void](/技术文档/客户端TS API/Unit/方法/remove_riseletter)

    * [set_riseletter_position(飘字:Class:Riseletter:3095523417,位置:Class:ScreenPos:3086221312):void](/技术文档/客户端TS API/Unit/方法/set_riseletter_position)

    * [set_disappear_destory_time(销毁时间:number):void](/技术文档/客户端TS API/Unit/方法/set_disappear_destory_time)

    * [create_riseletter_without_color_size(位置:UnionType,文字内容:string,漂浮文字样式:Preset:riseletter_id):Class:Riseletter:3095523417](/技术文档/客户端TS API/Unit/方法/create_riseletter_without_color_size)

    * [create_riseletter_with_color_size(位置:UnionType,文字内容:string,漂浮文字样式:Preset:riseletter_id,颜色:string,字号:number):Class:Riseletter:3095523417](/技术文档/客户端TS API/Unit/方法/create_riseletter_with_color_size)

    * [get_model_path():string](/技术文档/客户端TS API/Unit/方法/get_model_path)

    * [set_status_bar_visibility(可见性:boolean):void](/技术文档/客户端TS API/Unit/方法/set_status_bar_visibility)

    * [play_anim_ex(动画名:string,参数:Class:ICustomAnimParams:1416774859):Class:AnimHandle:3112051776](/技术文档/客户端TS API/Unit/方法/play_anim_ex)

    * [get_anims():Class:Array](/技术文档/客户端TS API/Unit/方法/get_anims)

  * 属性：

    * [_id_ (number)](/技术文档/客户端TS API/Unit/属性/id)

    * [_cache_ (Class:_OBJ__unit_Unit)](/技术文档/客户端TS API/Unit/属性/cache)

    * [__id_ (number)](/技术文档/客户端TS API/Unit/属性/_id)

  * 相关页面：

    * 面向对象: [单位](/技术文档/客户端面向对象 API/单位/Unit)

[上一页TriggerParamTable](/技术文档/客户端TS
API/TriggerParamTable/)[下一页cache](/技术文档/客户端TS API/Unit/属性/cache)


