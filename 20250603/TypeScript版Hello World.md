  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 代码开发必读
  * TypeScript版Hello World

复制链接

本页总览

# TypeScript版Hello World

使用ts来编写：当按下指定按键的时候输出"hello world"

## 服务端[​](/技术文档/代码开发必读/HelloWorld_TS#服务端 "服务端的直接链接")

  1. 首先我们需要在我们的触发编辑器中创建自定义脚本文件： ![](/assets/images/ts的创建-fbd8ddd63f7c29a7e4c8797ba821dc88.png)

  2. 在创建好文件后选择文本模式为：ts ![](/assets/images/选择ts-8516ea25715a808665feefd3576a75b5.png)

  3. 右键我们创建好的文件使用文本编辑器打开输入代码

    
    
    namespace p_gwca // 此处的命名空间填项目名（一般是p_xxxx格式）  
    {           
        const game = base.game;  
        //服务端有player，我们需要在这里加上player,且服务端的事件为"玩家-按键按下"  
        game.event("玩家-按键按下", (player: any, key: string) =>   
        {        
            if (key === "L") //对按下的键盘按键进行判断  
            {  
                log.info("这是我的键盘按键：" + key);  
                log.info("你好啊~星火编辑器");  
            }  
        });  
    }  
    

保存并调试发现服务端正常输出

![](/assets/images/new06-1fbe95a6a1ffde1e88da51358d79f5dc.png)

## 客户端[​](/技术文档/代码开发必读/HelloWorld_TS#客户端 "客户端的直接��链接")

同理客户端也进行同样的操作（注意"按键-按下"，在服务端与客户端表现不同，客户端中不需要写player参数），保存调试后也是正常输出

    
    
    namespace p_gwca // 此处的命名空间填项目名（一般是p_xxxx格式）  
    {           
        const game = base.game;  
        //客户端没有player，且客户端事件为"按键-按下"  
        game.event("按键-按下", (key: string) =>   
        {            
            if (key === "Q") //同理，对键盘按键进行判断  
            {  
                log.info("这是我的键盘按键：" + key);         
                log.info("你好啊~星火编辑器");  
            }  
        });  
    }  
    

![](/assets/images/new07-f1a98b738f4848bad0b602ba0161c4a0.png)

提示

用VS Code配合TypeScript开发时，可以对官方的类和函数使用Ctrl键+鼠标左键查看编辑器内类的定义和函数声明。

以服务端为例，此文件位置在：

`C:\星火编辑器\update\editor-{你的编辑器环境}.spark.xd.com\res\_m\maps\global_default\{版本号}\global_default\script\lua_declare.d.ts`

**标签：**

  * [TS](/tags/ts)
  * [代码开发](/tags/代码开发)

[上一页Lua版Hello, World](/技术文档/代码开发必读/HelloWorld_lua)[下一页Lua脚本简介](/技术文档/服务端Lua
API/简介)


