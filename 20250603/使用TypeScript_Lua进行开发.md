  * [](/)
  * 触发编辑器
  * 进阶功能
  * 使用TypeScript/Lua进行开发

复制链接

本页总览

# 使用TypeScript/Lua进行开发

具体的使用方法如下：

## 1\. 创建自定义文件[​](/Manual/TriggerEditor/Advanced/Code#1-创建自定义文件 "1.
创建自定义文件的直接链接")

  * 右键点击当前项目，或者点击右侧“+”号，在菜单中选择新建自定义文件；或者是当前项目下的文件夹的右侧“+”号，也能在该文件夹下创建自定义文件； ![](/assets/images/创建自定义文件-d0071b9b17299ac12846b02bb63ea24a.png)

  * 给自定义文件命名； ![](/assets/images/命名自定义文件-ede34d34a821e4005c643f28e5bfeea4.png)

  * 设置自定义文件类型，可选的有 lua / ts 文件； ![](/assets/images/设置自定义文件类型-1c79c63b4243b5d4da2484c12765128d.png)

## 2\. 打开文件进行编辑[​](/Manual/TriggerEditor/Advanced/Code#2-打开文件进行编辑 "2.
打开文件进行编辑的直接链接")

  * 右键自定义文件，菜单中可以用文本编辑器打开自定义文件； ![](/assets/images/右键菜单中打开自定义文件-4ad11d9b5bdb4411050471868df50668.png)

  * 在打开的文件中，编写自定义文件；

  * 由于触发生成的代码都在当前项目名的同名模块中，所以如果自定义文件中的类容希望被触发编辑器使用的话，需要放到当前项目名的同名全局变量下；在这里，是放到 `single_simple_ts_template_88_z6oa` 的 `module` 下面；

  * 如果自定义文件时创建在当前地图模块文件夹下面，在script中，实际的文件也会在对应路径的文件夹下；

![](/assets/images/编写自定义文件-72a7402cd49968f4cc1788b767f96bfe.png)

## 3\. 编写声明文件[​](/Manual/TriggerEditor/Advanced/Code#3-编写声明文件 "3.
编写声明文件的直接链接")

  * 给刚才手写的ts代码里的 `func` 函数编写声明文件； ![](/assets/images/新建声明文件-df37978cbcc2e713d9d0aefe1fd5c7b3.png)

  * 自定义文件下新建的内容都是isDeclare的声明文件，且不能被改变 ![](/assets/images/声明文件-701cb45f541ed4acca4b9160e2e6732c.png)

  * 在触发中通过声明文件使用我们手写的 `func` 函数；

###
注意：只有需要在触发器里调用的函数才需要在触发器图形化界面里声明，并不是所有的ts代码函数都需要手动声明。[​](/Manual/TriggerEditor/Advanced/Code#注意只有需要在触发器里调用的函数才需要在触发器图形化界面里声明并不是所有的ts代码函数都需要手动声明
"注意：只有需要在触发器里调用的函数才需要在触发器图形化界面里声明，并不是所有的ts代码函数都需要手动声明。的直接链接")

![](/assets/images/触发中调用func函数-0572c08c003f36cb77f86bf177430cd9.png)

## 4\. 运行游戏[​](/Manual/TriggerEditor/Advanced/Code#4-运行游戏 "4. 运行游戏的直接链接")

  * 运行游戏，可以看到 func 函数以符合预期的方式成功运行了； ![](/assets/images/自定义的文件成功运行-e88a7c424866a7b68e4c82afb072264f.png)

  * 可以看到，自定义文件 test_file，在 trigger_module_main 文件之后被引用，所有在触发里非自定义文件中实现的内容，现在都被生成到 trigger_module_main.ts 中；其中，自定义文件被引用的顺序，就是这些文件在触发左侧文件树中被遍历到的顺序；

  * 这里因为我们的自定义文件是ts代码，所以直接被拷贝到 script 下，实现代码中的内容的同时也提供了内容的声明；如果自定义文件是lua代码，除了拷贝lua代码以外，还会生成一份同名的 d.ts 文件，对lua中的内容进行声明；

![](/assets/images/保存时在script下生成的内容-f6b0b2ee0382cbd22a4997e982d841f7.png)

[上一页表结构](/Manual/TriggerEditor/Advanced/Table)[下一页类型编辑器使用指南](/Manual/TriggerEditor/Advanced/TypeEditor)


