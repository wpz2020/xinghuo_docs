  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端Lua API
  * 我们对Lua做的修改

复制链接

本页总览

# 我们对Lua做的修改

Lua版本基于5.3.4。为了安全性和其他一些因素考虑，我们对部分Lua标准api进行了定制。

## 文件系统[​](/技术文档/服务端Lua API/我们对Lua做的修改#文件系统 "文件系统的直接链接")

我们为你提供了受限的读取文件的能力，你可以使用`io.open`或`io.lines`读取地图的文件，例如

    
    
      local f = assert(io.open 'script/main.lua')  
      print(f:read 'a')  
      f:close()  
      
      for line in io.lines 'script/main.lua' do  
        print(line)  
      end  
    

但你无法通过`io.open`来修改一个文件。

!> 文件路径编码都是utf8

  * 加载器

你无法加载一个c模块，所以`package.loadlib`和`package.cpath`都是无效的。加载lua模块使用的是地图内的路径(和`io.open`一样)，默认的`package.path`是

    
    
    "script/?.lua;script/?/init.lua"  
    

## 不支持直接访问操作系统资源的API[​](/技术文档/服务端Lua API/我们对Lua做的修改#不支持直接访问操作系统资源的api
"不支持直接访问操作系统资源的API的直接链接")

包括

  * os.execute
  * os.exit
  * os.getenv
  * os.remove
  * os.rename
  * os.setlocale
  * os.tmpname
  * io.input
  * io.output
  * io.tmpfile
  * io.popen

## 随机数[​](/技术文档/服务端Lua API/我们对Lua做的修改#随机数 "随机数的直接链接")

我们定制了随机数发生器，以保证随机数不会受到外部因素的影响，并且我们关闭了`math.randomseed`。

## 额外添加了`debug_bp`函数[​](/技术文档/服务端Lua API/我们对Lua做的修改#额外添加了debug_bp函数
"额外添加了debug_bp函数的直接链接")

`debug_bp`被注册为一个全局函数

    
    
    if debug_bp then  
      debug_bp()  -- 如果当前已有调试器连接, 那么会强制在这一行进入断点  
    end  
    
    
    
    if debug_bp then  
      debug_bp(60 * 1000)  -- 如果没有现在调试器连接, 那么就等待新的调试器连接, 至多等待60秒  
    end  
    
    
    
    if debug_bp then  
      debug_bp(true)  -- 如果没有现在调试器连接, 那么就等待新的调试器连接, 无限等待时间, 直到有新的调试器连入  
    end  
    

!> 在正式环境不支持`debug_bp`

## 不支持从文件加载代码[​](/技术文档/服务端Lua API/我们对Lua做的修改#不支持从文件加载代码 "不支持从文件加载代码的直接链接")

包括

  * dofile
  * loadfile

## 部分支持`coroutine`[​](/技术文档/服务端Lua API/我们对Lua做的修改#部分支持coroutine
"部分支持coroutine的直接链接")

[上一页Lua脚本简介](/技术文档/服务端Lua API/简介)[下一页如果没用过Lua](/技术文档/服务端Lua API/如果没用过Lua)


