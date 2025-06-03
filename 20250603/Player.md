  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Player

复制链接

# Player

  * 类名：Player

  * 方法：

    * [controller():[PlayerController](/技术文档/枚举文档/PlayerController)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Player/方法/controller)

    * [get_hero():Class:Unit](/技术文档/服务端TS API/Player/方法/get_hero)

    * [lock_camera_by_mouse_wheel():void](/技术文档/服务端TS API/Player/方法/lock_camera_by_mouse_wheel)

    * [get_slot_id():number](/技术文档/服务端TS API/Player/方法/get_slot_id)

    * [lock_camera():void](/技术文档/服务端TS API/Player/方法/lock_camera)

    * [is_abort():boolean](/技术文档/服务端TS API/Player/方法/is_abort)

    * [kick(服务端记录:string,客户端记录:string):void](/技术文档/服务端TS API/Player/方法/kick)

    * [create_unit(单位Id:Preset:unit_id,位置:Class:Point,方向:number):UnionType](/技术文档/服务端TS API/Player/方法/create_unit)

    * [create_item(物品Id:Preset:item_id,位置:Class:Point):UnionType](/技术文档/服务端TS API/Player/方法/create_item)

    * [get_team_id():number](/技术文档/服务端TS API/Player/方法/get_team_id)

    * [game_state():[PlayerOnlineState](/技术文档/枚举文档/PlayerOnlineState)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Player/方法/game_state)

    * [add(玩家属性:Preset:玩家属性,数值:number):void](/技术文档/服务端TS API/Player/方法/add)

    * [get_num(玩家属性:Preset:玩家属性):number](/技术文档/服务端TS API/Player/方法/get_num)

    * [set_num(玩家属性:Preset:玩家属性,数值:number):void](/技术文档/服务端TS API/Player/方法/set_num)

    * [get(属性:Preset:玩家属性):any](/技术文档/服务端TS API/Player/方法/get)

    * [set(属性:Preset:玩家属性,值:any):void](/技术文档/服务端TS API/Player/方法/set)

    * [leave_reason():string](/技术文档/服务端TS API/Player/方法/leave_reason)

    * [set_afk():void](/技术文档/服务端TS API/Player/方法/set_afk)

    * [set_hero(单位:Class:Unit):void](/技术文档/服务端TS API/Player/方法/set_hero)

    * [set_team_id(队伍编号:number):void](/技术文档/服务端TS API/Player/方法/set_team_id)

    * [unlock_camera():void](/技术文档/服务端TS API/Player/方法/unlock_camera)

    * [user_agent():string](/技术文档/服务端TS API/Player/方法/user_agent)

    * [user_id():Class:用户id:3023175680](/技术文档/服务端TS API/Player/方法/user_id)

    * [user_info(类型:string):any](/技术文档/服务端TS API/Player/方法/user_info)

    * [user_level():number](/技术文档/服务端TS API/Player/方法/user_level)

    * [get_user_name():string](/技术文档/服务端TS API/Player/方法/get_user_name)

    * [get_nick_name():string](/技术文档/服务端TS API/Player/方法/get_nick_name)

    * [get_user_info(属性:string):any](/技术文档/服务端TS API/Player/方法/get_user_info)

    * [input_mouse():Class:Point](/技术文档/服务端TS API/Player/方法/input_mouse)

    * [input_rocker():number](/技术文档/服务端TS API/Player/方法/input_rocker)

    * [play_music(音效名:string):void](/技术文档/服务端TS API/Player/方法/play_music)

    * [play_sound(音效名:string):void](/技术文档/服务端TS API/Player/方法/play_sound)

    * [camera_focus(unit:Class:Unit):void](/技术文档/服务端TS API/Player/方法/camera_focus)

    * [is_online():boolean](/技术文档/服务端TS API/Player/方法/is_online)

    * [get_match_team_id():number](/技术文档/服务端TS API/Player/方法/get_match_team_id)

    * [alliance_state(另一个玩家:Class:Player):[AllianceState](/技术文档/枚举文档/AllianceState)](/技术文档/%E6%9C%8D%E5%8A%A1%E7%AB%AFTS%20API/Player/方法/alliance_state)

    * [is_neutral():boolean](/技术文档/服务端TS API/Player/方法/is_neutral)

    * [set_is_neutral(中立状态:boolean):void](/技术文档/服务端TS API/Player/方法/set_is_neutral)

    * [toggle_force_share_sight(另一个玩家:Class:Player,开关:boolean):void](/技术文档/服务端TS API/Player/方法/toggle_force_share_sight)

    * [share_sight_to_player(other:Class:Player):void](/技术文档/服务端TS API/Player/方法/share_sight_to_player)

    * [remove_share_sight_to_player(other:Class:Player):void](/技术文档/服务端TS API/Player/方法/remove_share_sight_to_player)

    * [event_notify(事件名:string):void](/技术文档/服务端TS API/Player/方法/event_notify)

    * [set_nick_name(新昵称:string):void](/技术文档/服务端TS API/Player/方法/set_nick_name)

    * [set_hero_skill_sync_type(sync_type:SyncType):void](/技术文档/服务端TS API/Player/方法/set_hero_skill_sync_type)

    * [clear_hero():void](/技术文档/服务端TS API/Player/方法/clear_hero)

    * [event_stat(事件名:string,表:Class:LuaTable):void](/技术文档/服务端TS API/Player/方法/event_stat)

  * 属性：

    * [_id_ (number)](/技术文档/服务端TS API/Player/属性/id)
  * 相关页面：

    * 面向对象: [玩家](/技术文档/服务端面向对象 API/玩家/Player)

[上一页remove](/技术文档/服务端TS API/Mover/方法/remove)[下一页id](/技术文档/服务端TS
API/Player/属性/id)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Player

复制链接

# Player

  * 类名：Player

  * 方法：

    * [game_state():[PlayerOnlineState](/技术文档/枚举文档/PlayerOnlineState)](/技术文档/%E5%AE%A2%E6%88%B7%E7%AB%AFTS%20API/Player/方法/game_state)

    * [get(玩家自定义属性:Preset:玩家属性):any](/技术文档/客户端TS API/Player/方法/get)

    * [get_hero():Class:Unit](/技术文档/客户端TS API/Player/方法/get_hero)

    * [get_slot_id():number](/技术文档/客户端TS API/Player/方法/get_slot_id)

    * [event_notify(事件名称:string):void](/技术文档/客户端TS API/Player/方法/event_notify)

    * [get_nick_name():string](/技术文档/客户端TS API/Player/方法/get_nick_name)

    * [is_neutral():boolean](/技术文档/客户端TS API/Player/方法/is_neutral)

    * [alliance_state(另一个玩家:Class:Player):[AllianceState](/技术文档/枚举文档/AllianceState)](/技术文档/%E5%AE%A2%E6%88%B7%E7%AB%AFTS%20API/Player/方法/alliance_state)

    * [get_team_id():number](/技术文档/客户端TS API/Player/方法/get_team_id)

    * [get_num(玩家数值属性:Preset:玩家属性):number](/技术文档/客户端TS API/Player/方法/get_num)

  * 属性：

    * [_id_ (number)](/技术文档/客户端TS API/Player/属性/id)
  * 相关页面：

    * 面向对象: [玩家](/技术文档/客户端面向对象 API/玩家/Player)

[上一页get_stack](/技术文档/客户端TS API/Item/方法/get_stack)[下一页id](/技术文档/客户端TS
API/Player/属性/id)


