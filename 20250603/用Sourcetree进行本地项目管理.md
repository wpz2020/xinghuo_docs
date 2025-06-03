  * [](/)
  * 协作开发
  * 用Sourcetree进行本地项目管理

复制链接

本页总览

# 用Sourcetree进行本地项目管理

Sourcetree是一个可视化的项目管理工具，本案例只涉及最简单的本地项目管理方法，协作、代码管理、权限管理等问题，本案例均不涉及

## Sourcetree的下载[​](/Manual/VersionControl/Sourcetree#sourcetree的下载
"Sourcetree的下载的直接链接")

从Sourcetree官网下载Windows版本客户端，如截图所示

![](https://doc.sce.xd.com/assets/images/4_1-20bd7386ea85142e0352f90588902da3.png)

## Sourcetree的安装[​](/Manual/VersionControl/Sourcetree#sourcetree的安装
"Sourcetree的安装的直接链接")

这一步可以选跳过，不需要注册Bitbucket的账户

![](https://doc.sce.xd.com/assets/images/4_2-00b754d7796c500a9778575fff8f8da0.png)

这一步会默认勾选安装Git和Mercurial，不需要进行修改，勾选安装即可

![](https://doc.sce.xd.com/assets/images/4_3-99f30a9c90ec00cbcc948c004fc3dce8.png)

这一步输入用户名和邮箱，由于我们是本地管理，可以随便输入

![](https://doc.sce.xd.com/assets/images/4_4-3317acc9cbea86dad32bddb6479e24c7.png)

##
Sourcetree的使用：创建自己的版本管理目标项目[​](/Manual/VersionControl/Sourcetree#sourcetree的使用创建自己的版本管理目标项目
"Sourcetree的使用：创建自己的版本管理目标项目的直接链接")

装好以后，启动sourcetree，为自己创建一个新的Tab，点击图中的Create
![](https://doc.sce.xd.com/assets/images/4_5-5137d3ccf949c2ce0bf27980b092b3fc.png)

点击浏览，选择你的星火项目所在的文件夹

![](https://doc.sce.xd.com/assets/images/4_6-071b8203441fcd912adf9fa644d125c1.png)

提醒文件已存在，是否创建仓库，选择『是』

![](https://doc.sce.xd.com/assets/images/4_7-79c2ea019581e7512ac534175eee4c63.png)

第一次创建好后，项目文件还没有纳入版本管理中，请点击暂存所有，再提交，创建你的初始版本

![](https://doc.sce.xd.com/assets/images/4_8-19d4d7d76bcfa4b1f4164b2a4130d465.png)

每次提交都可以写一些信息，用来区分版本或者改动

![](https://doc.sce.xd.com/assets/images/4_9-9f7003429d755463995e7898964616d0.png)

提交后，即创建出了这样一个master工程版本

![](https://doc.sce.xd.com/assets/images/4_10-44a8c25015355956364670df6592d843.png)

##
Sourcetree的使用：修改原始版本，构造新的版本[​](/Manual/VersionControl/Sourcetree#sourcetree的使用修改原始版本构造新的版本
"Sourcetree的使用：修改原始版本，构造新的版本的直接链接")

在星火编辑器中打开这个项目，进行一些修改，并且保存项目

![](https://doc.sce.xd.com/assets/images/4_11-5009ce479d7ba7d47aae9d2e066806c6.png)

这里能看到一批修改过的文件出现在这个区域

![](https://doc.sce.xd.com/assets/images/4_12-37f23e3499d164fdd49e6d618eb260f1.png)

将这些文件全部保存，并且点击提交，将新的版本保存为2.0版本

![](https://doc.sce.xd.com/assets/images/4_13-9b1382fbc007bd929c0c85c8cbeade67.png)

这时候就可以看到，同时存在了『最初的工程版本』和『2.0版本』

![](https://doc.sce.xd.com/assets/images/4_14-0dded7d9d56c0289c399643959521bb1.png)

当前处于『2.0版本』，但是我们发现2.0版本改错了，想回退到之前的旧版

于是双击『最初的工程版本』，弹出提醒，点击确定

![](https://doc.sce.xd.com/assets/images/4_15-d02a8c5d9274e63bb149c16d9c8afaed.png)

这样我们就切换回了『最初的工程版本』，再双击『2.0版本』，又可以切回『2.0版本』

![](https://doc.sce.xd.com/assets/images/4_16-e778fcfa66ac028092e3d785360f9c06.png)

##
Sourcetree的使用：抛弃修改过的文件[​](/Manual/VersionControl/Sourcetree#sourcetree的使用抛弃修改过的文件
"Sourcetree的使用：抛弃修改过的文件的直接链接")

如果我们基于当前的版本，做了修改，但是又想重置回修改的状态，则需要将『未暂存的文件』丢弃
有时候大家会发现无法双击切换，往往也是因为有『未暂存的文件』需要先丢弃处理

![](https://doc.sce.xd.com/assets/images/4_17-08553f8e361c5fe6fda177c917c85783.png)

![](https://doc.sce.xd.com/assets/images/4_18-7a5ee2f9feb9ef13fa2173fd58d1e20b.png)

[上一页如何添加协作者一起协同开发项目](/Manual/VersionControl/Cooperation)[下一页星火编辑器项目内文件夹介绍](/Manual/VersionControl/FolderDescription)


