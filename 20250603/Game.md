  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Game

复制链接

# Game

  * 类名：Game

  * 模块：base

  * tips:`对应游戏局`

  * 方法：

    * [event_notify(事件名称:string):void](/技术文档/服务端TS API/Game/方法/event_notify)

    * [set_winner(unused:number):void](/技术文档/服务端TS API/Game/方法/set_winner)

    * [load_scene(场景:Preset:Scene):Class:SceneObject:3021886274](/技术文档/服务端TS API/Game/方法/load_scene)

    * [close_scene(场景:Preset:Scene):boolean](/技术文档/服务端TS API/Game/方法/close_scene)

    * [create_scene_copy(模版场景:Preset:Scene,副本场景名称:string):boolean](/技术文档/服务端TS API/Game/方法/create_scene_copy)

    * [get(attribute:Preset:游戏属性):UnionType](/技术文档/服务端TS API/Game/方法/get)

    * [set(attribute:Preset:游戏属性,value:UnionType):void](/技术文档/服务端TS API/Game/方法/set)

    * [create_team():number](/技术文档/服务端TS API/Game/方法/create_team)

    * [get_all_team_id():Class:Array](/技术文档/服务端TS API/Game/方法/get_all_team_id)

    * [get_scene_object(新参数:Preset:Scene):Class:SceneObject:3021886274](/技术文档/服务端TS API/Game/方法/get_scene_object)

    * [get_scene_object_list():Class:Array](/技术文档/服务端TS API/Game/方法/get_scene_object_list)

    * [get_scene_object_by_key(场景名称:string):Class:SceneObject:3021886274](/技术文档/服务端TS API/Game/方法/get_scene_object_by_key)

    * [load_create_scene_copy(模版场景:Preset:Scene,副本场景名称:string):Class:SceneObject:3021886274](/技术文档/服务端TS API/Game/方法/load_create_scene_copy)

    * [time_stop(时长:number,不暂停游戏时间:boolean):void](/技术文档/服务端TS API/Game/方法/time_stop)

    * [cancel_time_stop():void](/技术文档/服务端TS API/Game/方法/cancel_time_stop)

    * [get_default_scene_name():Preset:Scene](/技术文档/服务端TS API/Game/方法/get_default_scene_name)

    * [control_game_speed(速度值:number):void](/技术文档/服务端TS API/Game/方法/control_game_speed)

    * [set_surrounding_scene(指定场景:Preset:Scene,上:Preset:Scene,左:Preset:Scene,下:Preset:Scene,右:Preset:Scene):void](/技术文档/服务端TS API/Game/方法/set_surrounding_scene)

  * 相关页面：

    * 面向对象: [游戏](/技术文档/服务端面向对象 API/游戏/Game)

[上一页phase](/技术文档/服务端TS
API/EffectParamShared/属性/phase)[下一页event_notify](/技术文档/服务端TS
API/Game/方法/event_notify)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Game

复制链接

# Game

  * 类名：Game

  * 模块：base

  * 方法：

    * [event_notify(事件名称:string):void](/技术文档/客户端TS API/Game/方法/event_notify)

    * [object_restore_value(对象:object,Key:string):any](/技术文档/客户端TS API/Game/方法/object_restore_value)

    * [object_store_value(对象:object,Key:string,值:any):void](/技术文档/客户端TS API/Game/方法/object_store_value)

    * [Static create_debug_draw_actor():Class:Actor879493120](/技术文档/客户端TS API/Game/方法/create_debug_draw_actor)

    * [Static debug_draw_point(表现:Class:Actor879493120,位置:Class:Point,颜色:string):void](/技术文档/客户端TS API/Game/方法/debug_draw_point)

    * [Static debug_draw_circle(表现:Class:Actor879493120,点:Class:Point,Alpha:number,Beta:number,Gamma:number,半径:number,颜色:string,是否填充内部:boolean):void](/技术文档/客户端TS API/Game/方法/debug_draw_circle)

    * [Static debug_draw_line(表现:Class:Actor879493120,起点:Class:Point,终点:Class:Point,颜色:string):void](/技术文档/客户端TS API/Game/方法/debug_draw_line)

    * [Static debug_draw_sector(表现:Class:Actor879493120,圆心:Class:Point,Alpha:number,Beta:number,Gamma:number,半径:number,角度:number,颜色:string,是否填充:boolean):void](/技术文档/客户端TS API/Game/方法/debug_draw_sector)

    * [Static debug_draw_text(表现:Class:Actor879493120,点:Class:Point,文本:string,颜色:string):void](/技术文档/客户端TS API/Game/方法/debug_draw_text)

    * [Static debug_draw_rectangle(表现:Class:Actor879493120,绘制点:Class:Point,宽边顶点偏移:Class:Point,高边顶点偏移:Class:Point,颜色:string,是否填充:boolean):void](/技术文档/客户端TS API/Game/方法/debug_draw_rectangle)

    * [Static clear_debug_draws(表现:Class:Actor879493120):void](/技术文档/客户端TS API/Game/方法/clear_debug_draws)

    * [server(类型:string):FuncType](/技术文档/客户端TS API/Game/方法/server)

    * [load_combined_map(场景:Preset:Scene,方向:Preset:_OBJ__ComBinedMapDirection):void](/技术文档/客户端TS API/Game/方法/load_combined_map)

    * [purge_combined_map():void](/技术文档/客户端TS API/Game/方法/purge_combined_map)

    * [load_combined_map_deco(场景:Preset:Scene,方向:Preset:_OBJ__ComBinedMapDirection):void](/技术文档/客户端TS API/Game/方法/load_combined_map_deco)

    * [purge_combined_map_deco():void](/技术文档/客户端TS API/Game/方法/purge_combined_map_deco)

    * [Static get_model_anim_point_info(模型路径:string,动画名:string):Class:AnimPointInfo:1576456933](/技术文档/客户端TS API/Game/方法/get_model_anim_point_info)

    * [one_more_round():void](/技术文档/客户端TS API/Game/方法/one_more_round)

  * 相关页面：

    * 面向对象: [游戏客户端](/技术文档/客户端面向对象 API/游戏客户端/Game)

[上一页is_closed](/技术文档/客户端TS
API/EffectParamShared/方法/is_closed)[下一页event_notify](/技术文档/客户端TS
API/Game/方法/event_notify)


