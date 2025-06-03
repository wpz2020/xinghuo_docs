  * [](/)
  * 创作者中心
  * 开发阶段常用功能
  * 如何将游戏独立导出为 PC 或 Android 包

复制链接

本页总览

# 如何将游戏独立导出为 PC 或 Android 包

目前，我们对导出游戏有了更加开放的策略，希望能够为开发者提供更自由的选择，所以我们新增了可以将自己的游戏独立导出为 PC 应用或 Android 包的功能。

要注意的是：

  * 只有在星火编辑器内发布过的项目才能进行导出
  * 独立打包的项目，我们从合规角度无法提供内购等功能，所以相关内容都需要开发者自行处理
  * 独立打包功能需要13版本的编辑器才支持，如果看到文档的时候13版本还没有发布，请耐心等待

## PC 步骤[​](/Manual/Developer/DevStage/IndependentExport#pc-步骤 "PC 步骤的直接链接")

  1. 在文件中，找到【导出为独立包】，选择 Windows

![](https://doc.sce.xd.com/assets/images/打开导入-3244273bea8bc9e4aa2bba7174ccc2ed.png)

  2. 输入项目名称

  3. 上传 .ico 格式的图标

  4. 选择一键导出进入远端构建，构建时不可进行操作

  5. 构建完成后即可下载运行

## Android 步骤[​](/Manual/Developer/DevStage/IndependentExport#android-步骤
"Android 步骤的直接链接")

  1. 在文件中，找到【导出为独立包】，选择 Android
  2. 输入项目名称
  3. 在[Tap 开发者服务](https://developer.taptap.cn/)注册成为开发者
  4. 创建游戏，在游戏服务里开启应用配置

![](https://doc.sce.xd.com/assets/images/游戏服务-6883bb03cce63ddb1b8e4fbf64dcdfd4.png)

  5. 在基本信息中，拿到生成的 ClientID 和 ClientToken，对应填入编辑器内

![](https://doc.sce.xd.com/assets/images/添加对应-84be08b2507632d73de7dc74fcdea04a.png)

  6. 在下方的签名证书配置中新增安卓包，填入包名和签名

![](https://doc.sce.xd.com/assets/images/新增安卓包-b80e24a8591c9ad82f6d85a567743fff.png)

  7. 包名复制项目包名即可；签名的获取方式请参考[Android 平台获取 MD5](https://developer.taptap.cn/docs/sdk/access/android-md5/)

![](https://doc.sce.xd.com/assets/images/包名-6892ecc3bb3d545a1e28d959dd463392.png)

  8. 上传 .png 格式的图标
  9. 选择一键导出进入远端构建，构建时不可进行操作
  10. 构建完成后即可下载运行

[上一页如何配置PVP对抗模式](/Manual/Developer/DevStage/PlayerVsPlayer)[下一页如何查看玩家的客户端日志](/Manual/Developer/OpStage/DevLog)


