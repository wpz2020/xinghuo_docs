  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端TS API
  * Actor

复制链接

# Actor

  * 类名：Actor

  * 方法：

    * [set_ground_z(相对高度:number):void](/技术文档/服务端TS API/Actor/方法/set_ground_z)

    * [set_position(位置:Class:Point):void](/技术文档/服务端TS API/Actor/方法/set_position)

    * [set_facing(朝向:number):void](/技术文档/服务端TS API/Actor/方法/set_facing)

    * [destroy(强制:boolean):void](/技术文档/服务端TS API/Actor/方法/destroy)

    * [set_asset(资源:UnionType):void](/技术文档/服务端TS API/Actor/方法/set_asset)

    * [set_owner(玩家:Class:Player):void](/技术文档/服务端TS API/Actor/方法/set_owner)

    * [set_shadow(是否显示影子:boolean):void](/技术文档/服务端TS API/Actor/方法/set_shadow)

    * [set_scale(缩放:number):void](/技术文档/服务端TS API/Actor/方法/set_scale)

    * [play():void](/技术文档/服务端TS API/Actor/方法/play)

    * [stop():void](/技术文档/服务端TS API/Actor/方法/stop)

    * [pause():void](/技术文档/服务端TS API/Actor/方法/pause)

    * [resume():void](/技术文档/服务端TS API/Actor/方法/resume)

    * [set_volume(音量:number):void](/技术文档/服务端TS API/Actor/方法/set_volume)

    * [set_launch_ground_z(z:number):void](/技术文档/服务端TS API/Actor/方法/set_launch_ground_z)

    * [set_launch_scene_point(坐标:Class:Point):void](/技术文档/服务端TS API/Actor/方法/set_launch_scene_point)

    * [set_launch_site(单位:Class:Unit,绑点:string):void](/技术文档/服务端TS API/Actor/方法/set_launch_site)

    * [set_text(文字:string):void](/技术文档/服务端TS API/Actor/方法/set_text)

    * [set_scale_xyz(X轴缩放:number,Y轴缩放:number,Z轴缩放:number):void](/技术文档/服务端TS API/Actor/方法/set_scale_xyz)

  * 属性：

    * [_cache_ (Class:_OBJ__actor_Actor)](/技术文档/服务端TS API/Actor/属性/cache)
  * 相关页面：

    * 面向对象: [表现](/技术文档/服务端面向对象 API/表现/Actor)

[上一页set_threat](/技术文档/服务端TS
API/AISearcher/方法/set_threat)[下一页cache](/技术文档/服务端TS API/Actor/属性/cache)


  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端TS API
  * Actor

复制链接

# Actor

  * 类名：Actor

  * 方法：

    * [set_facing(朝向:number):void](/技术文档/客户端TS API/Actor/方法/set_facing)

    * [destroy(表现摧毁方式:ActorDestructionType):void](/技术文档/客户端TS API/Actor/方法/destroy)

    * [set_asset(模型资源:Preset:model_id):void](/技术文档/客户端TS API/Actor/方法/set_asset)

    * [set_owner(玩家号:number):void](/技术文档/客户端TS API/Actor/方法/set_owner)

    * [set_shadow(是否:boolean):void](/技术文档/客户端TS API/Actor/方法/set_shadow)

    * [actor_set_scale(缩放值:number):void](/技术文档/客户端TS API/Actor/方法/actor_set_scale)

    * [play():void](/技术文档/客户端TS API/Actor/方法/play)

    * [stop():void](/技术文档/客户端TS API/Actor/方法/stop)

    * [pause():void](/技术文档/客户端TS API/Actor/方法/pause)

    * [resume():void](/技术文档/客户端TS API/Actor/方法/resume)

    * [set_volume(音量:number):void](/技术文档/客户端TS API/Actor/方法/set_volume)

    * [set_ground_z(高度:number):void](/技术文档/客户端TS API/Actor/方法/set_ground_z)

    * [get_socket_rotation(绑点:string):Class:XYZ旋转:1136001024](/技术文档/客户端TS API/Actor/方法/get_socket_rotation)

    * [get_socket_position(绑点:string):Class:Point](/技术文档/客户端TS API/Actor/方法/get_socket_position)

    * [attach_to(目标:UnionType,绑点:string):void](/技术文档/客户端TS API/Actor/方法/attach_to)

    * [set_rotation(X轴:number,Y轴:number,Z轴:number):void](/技术文档/客户端TS API/Actor/方法/set_rotation)

    * [set_position(X轴:number,Y轴:number,Z轴:number):void](/技术文档/客户端TS API/Actor/方法/set_position)

    * [set_launch_scene_point(坐标:Class:Point):void](/技术文档/客户端TS API/Actor/方法/set_launch_scene_point)

    * [set_launch_ground_z(z:number):void](/技术文档/客户端TS API/Actor/方法/set_launch_ground_z)

    * [set_launch_site(单位:Class:Unit,绑点:string):void](/技术文档/客户端TS API/Actor/方法/set_launch_site)

    * [set_text(文字:string):void](/技术文档/客户端TS API/Actor/方法/set_text)

    * [set_scale_xyz(X轴缩放:number,Y轴缩放:number,Z轴缩放:number):void](/技术文档/客户端TS API/Actor/方法/set_scale_xyz)

    * [play_anim_ex(动画名:string,参数:Class:ICustomAnimParams:1416774859):Class:AnimHandle:3112051776](/技术文档/客户端TS API/Actor/方法/play_anim_ex)

    * [get_anims():Class:Array](/技术文档/客户端TS API/Actor/方法/get_anims)

    * [set_destroy_on_orphan():void](/技术文档/客户端TS API/Actor/方法/set_destroy_on_orphan)

    * [is_destroy_on_orphan():boolean](/技术文档/客户端TS API/Actor/方法/is_destroy_on_orphan)

  * 属性：

    * [_cache_ (Class:_OBJ__actor_Actor)](/技术文档/客户端TS API/Actor/属性/cache)

    * [__name_ (Preset:actor_id)](/技术文档/客户端TS API/Actor/属性/_name)

  * 相关页面：

    * 面向对象: [表现](/技术文档/客户端面向对象 API/表现/Actor)

[上一页from_data_field](/技术文档/服务端TS
API/target_filters/方法/from_data_field)[下一页cache](/技术文档/客户端TS
API/Actor/属性/cache)


