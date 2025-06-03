  * [](/)
  * UGC小游戏
  * SCE Game SDK 使用指南

复制链接

本页总览

# SCE Game SDK 使用指南

## 简介[​](/UGCXiaoYouXi/sce-game-sdk#简介 "简介的直接链接")

SCE Game SDK 是一个专为在 **星火对战平台** 中开发小游戏设计的 TypeScript
工具包。它提供了一系列便捷的功能，如登录验证、云数据存储和排行榜等，旨在帮助开发者快速构建和集成他们的小游戏。

开发者可以通过此 SDK 轻松管理用户数据、存储游戏状态，并实现具有竞争性的排行榜功能。

详细的 API 文档和最新信息请参考官方 NPM 页面：<https://www.npmjs.com/package/sce-game-sdk>

## 详细用法与 AI 集成建议[​](/UGCXiaoYouXi/sce-game-sdk#详细用法与-ai-集成建议 "详细用法与 AI
集成建议的直接链接")

本文档主要面向希望快速上手或借助 AI 工具（如
Cursor）进行开发的非专业用户。对于每个接口的**具体参数、详细的请求/响应格式、错误处理以及更深入的使用示例** ，强烈建议开发者直接查阅官方 NPM
文档页面：

[**SCE Game SDK NPM 主页**](https://www.npmjs.com/package/sce-game-sdk)

当您需要使用 AI 辅助工具（如 Cursor 或其他代码助手）来帮助集成 SDK 的特定功能时，请**直接向 AI 提供 NPM
页面的链接或相关代码片段** 。AI 可以基于该官方文档为您生成更准确、更具体的代码实现。

例如，您可以这样提问：

> "请参考 <https://www.npmjs.com/package/sce-game-sdk> 上的文档，使用 Promise 风格为我生成一个调用
> `SceSDK.cloud.set_data` 方法来存储玩家背包数据的 TypeScript 代码示例，键名为
> `player_inventory`。"

通过这种方式，可以确保 AI 获取到最新、最准确的 API 信息，从而提高代码生成的质量和效率。

## 安装[​](/UGCXiaoYouXi/sce-game-sdk#安装 "安装的直接链接")

您可以通过以下两种主要方式将 SCE Game SDK 集成到您的项目中：

### 1\. 通过 npm 安装[​](/UGCXiaoYouXi/sce-game-sdk#1-通过-npm-安装 "1. 通过 npm
安装的直接链接")

确保您已安装 Node.js (版本 >=16.0.0)。然后在您的项目目录下运行：

    
    
    npm install sce-game-sdk  
    

在您的 TypeScript 或 JavaScript 文件中导入 SDK：

    
    
    import 'sce-game-sdk';  
    // 或者根据您的项目配置可能需要 const SceSDK = require('sce-game-sdk');  
    

### 2\. CDN 直接引入[​](/UGCXiaoYouXi/sce-game-sdk#2-cdn-直接引入 "2. CDN 直接引入的直接链接")

如果您希望直接在 HTML 文件中使用，可以将以下 `<script>` 标签添加到您的 HTML 文件的 `<head>` 或 `<body>` 部分：

    
    
    <script src="https://cdn.jsdelivr.net/npm/sce-game-sdk@latest/dist/sce.min.js"></script>  
    <!-- 或者 -->  
    <script src="https://unpkg.com/sce-game-sdk@latest/dist/sce.min.js"></script>  
    

通过 CDN 引入后，全局对象 `SceSDK` 将立即可用，您可以直接通过它来调用所有 SDK 功能。

## 调用方式[​](/UGCXiaoYouXi/sce-game-sdk#调用方式 "调用方式的直接链接")

SCE Game SDK 支持两种主流的异步调用风格：

  * **Promise 风格** ：这是现代 JavaScript 中推荐的异步处理方式，可以使代码更易于阅读和管理，特别是配合 `async/await` 语法。
  * **回调风格** ：对于标记为支持回调的接口，您可以在最后一个参数传入一个包含 `success` 和 `fail` 方法的对象来处理异步结果。

开发者可以根据自己的项目需求和编码习惯选择最适合的调用方式。

## 主要功能概览[​](/UGCXiaoYouXi/sce-game-sdk#主要功能概览 "主要功能概览的直接链接")

以下是 SCE Game SDK 提供的一些核心功能：

### 1\. 初始化与配置 (SceSDK.init_for_dev)[​](/UGCXiaoYouXi/sce-game-sdk#1-初始化与配置-
scesdkinit_for_dev "1. 初始化与配置 \(SceSDK.init_for_dev\)的直接链接")

在非星火平台的开发环境中调试 SDK 时，需要进行初始化配置。在星火平台的正式运行环境中，SDK 会自动初始化，无需开发者手动调用。

  * **`SceSDK.init_for_dev(options)`** : 需要传入包含 `sce_developer_token` 的 `options` 对象。此 token 可从星火编辑器的创作者中心获取。

### 2\. 获取玩家信息 (SceSDK.get_user_info)[​](/UGCXiaoYouXi/sce-game-sdk#2-获取玩家信息-
scesdkget_user_info "2. 获取玩家信息 \(SceSDK.get_user_info\)的直接链接")

用于获取当前登录到星火平台的用户信息。

  * **返回** : 包含 `user_id` (用户SCEID) 和 `name` (用户TapTap昵称) 的对象。

### 3\. 云数据存储[​](/UGCXiaoYouXi/sce-game-sdk#3-云数据存储 "3. 云数据存储的直接链接")

SDK 提供了便捷的云端数据存储能力，包括对象类型和专用于排名的数值类型数据。

  * **`SceSDK.cloud.set_data(key, value)`** : 存储任意对象类型的数据。
  * **`SceSDK.cloud.get_data(key)`** : 获取之前存储的对象类型数据。
  * **`SceSDK.cloud.set_number(key, value)`** : 存储数值类型数据，通常用于排行榜积分。
  * **`SceSDK.cloud.get_number(key)`** : 获取存储的数值类型数据。

### 4\. 排行榜功能[​](/UGCXiaoYouXi/sce-game-sdk#4-排行榜功能 "4. 排行榜功能的直接链接")

基于 `set_number` 存储的数值，可以轻松实现排行榜功能。

  * **`SceSDK.cloud.get_top_rank(options)`** : 获取排行榜数据，可以指定榜单key、数量限制、是否包含用户名以及排序方式等。
  * **`SceSDK.cloud.get_user_rank(options)`** : 查询特定用户在某个排行榜上的排名和数值，不传用户ID则查询当前登录用户。

[上一页UGC小游戏自动发布&部署指南](/UGCXiaoYouXi/auto-deploy-cli)


