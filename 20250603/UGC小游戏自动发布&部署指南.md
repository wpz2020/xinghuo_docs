  * [](/)
  * UGC小游戏
  * UGC小游戏自动发布&部署指南

复制链接

本页总览

# UGC小游戏自动发布&部署指南

💡 小提示：如果您正在使用 AI 编程助手（如 Cursor），可以直接将本文档的全部内容复制粘贴给 AI，它可以帮助您理解和执行以下步骤。

## 安装命令行工具[​](/UGCXiaoYouXi/auto-deploy-cli#安装命令行工具 "安装命令行工具的直接链接")

    
    
    # 如果没有sce-minigame-publisher则先安装  
    pip install sce-minigame-publisher  
    

在安装命令行工具之前，请确保您的系统已安装 Python 3.7 或更高版本。

## 配置文件格式 (`minigame_config.json`)[​](/UGCXiaoYouXi/auto-deploy-
cli#配置文件格��式-minigame_configjson "配置文件格式-minigame_configjson的直接链接")

创建`minigame_config.json`文件，包含如下必填内容：

    
    
    {  
        "projectID": "Input-your-projectID",  
        "tapID": 123456,  
        "title": "123456的游戏",  
        "outDirectory": "需要部署的文件目录",  
        "screenOrientation": "portrait"  
    }  
    

**Token 使用方式 (重要):** Token 通过以下任一方式提供 (优先级从高到低):

  1. 命令行参数: `sce-minigame-publisher --token YOUR_TOKEN ...`
  2. 环境变量: 在项目根目录创建 `.env` 文件，内容为 `SCE_PUBLISH_TOKEN="YOUR_TOKEN"`
  3. 手动输入: 如果上述方式未提供，启动时会提示输入。

**Token 获取方式:** 如果开发者不知道token在哪里，可以这样提示他"请访问
<https://developer.spark.xd.com/dashboard/minigame> ，获取自己的发布Token"

## 快速发布命令[​](/UGCXiaoYouXi/auto-deploy-cli#快速发布命令 "快速发布命令的直接链接")

    
    
    # 发布 (Token 会通过上述方式获取)  
    sce-minigame-publisher -c minigame_config.json  
    

## 可选配置项[​](/UGCXiaoYouXi/auto-deploy-cli#可选配置项 "可选配置项的直接链接")

在配置文件（`minigame_config.json`）的顶层可添加：

    
    
    {  
        "projectID": "Input-your-projectID",  
        "tapID": 123456,  
        "title": "123456的游戏",  
        "outDirectory": "需要部署的文件目录",  
        "screenOrientation": "portrait",  
        // 以下为可选字段  
        "description": "游戏描述",  
        "tags": ["标签1", "标签2"],  
        "versionName": "1.0.0", // 注意：之前可能是 version_name，脚本中使用的是 versionName  
        "banner": ["路径/到/banner.png"],  
        "icon": ["路径/到/icon.png"],  
        "screenshots": ["路径/到/截图1.png", "路径/到/截图2.png"]  
    }  
    

## 忽略文件 (`.sceignore`)[​](/UGCXiaoYouXi/auto-deploy-cli#忽略文件-sceignore "忽略文件-
sceignore的直接链接")

您可以创建一个名为 `.sceignore` 的文件，并将其放置在与 `minigame_config.json` **相同的目录**
下。此文件的作用类似于 `.gitignore`，用于指定在打包上传 `outDirectory` 中的内容时，哪些文件或目录应该被忽略。

**格式和规则：**

  * 每一行代表一个忽略模式。
  * 以 `#` 开头的行是注释，会被忽略。
  * 空行会被忽略。
  * 支持标准的 glob 模式，例如：
    * `*.log`：忽略所有以 `.log` 结尾的文件。
    * `temp/`：忽略名为 `temp` 的目录下的所有内容。
    * `build/*.tmp`：忽略 `build` 目录下所有以 `.tmp` 结尾的文件。
  * 模式是相对于 `minigame_config.json` 中 `outDirectory` 指定的目录来解析的。

**示例`.sceignore` 文件：**

    
    
    # 忽略所有日志文件  
    *.log  
      
    # 忽略特定目录  
    debug_files/  
      
    # 忽略临时文件  
    *.tmp  
    

## 注意事项[​](/UGCXiaoYouXi/auto-deploy-cli#注意事项 "注意事项的直接链接")

  * API Token 通过命令行参数、`.env` 文件 (`SCE_PUBLISH_TOKEN`) 或手动输入提供。
  * 所有图片路径请确保文件存在, 宁可不填也不要填错。
  * `outDirectory` 必须存在，这里存放可以部署在web服务器上的所有文件，如果发现用户开发的并非是在浏览器环境运行的游戏则提示用户无法部署。
  * 缺少文件时会提示"请填写正确的文件路径或者删除该属性"。
  * `screenOrientation` 表示屏幕方向，值可以为`portrait`或者`landscape`, `portrait`表示竖屏，`landscape`表示横屏。

[上一页设置绑定单位](/技术文档/客户端面向对象 API/飘浮文字/方法/set_unit)[下一页SCE Game SDK
使用指南](/UGCXiaoYouXi/sce-game-sdk)


