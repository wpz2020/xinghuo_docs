  * [](/)
  * 界面编辑器
  * UI案例与最佳实践
  * 如何通过修改布局做到UI自适应

复制链接

本页总览

# 如何通过修改布局做到UI自适应

阅读此文档前，请确保读者已阅读过[界面编辑器介绍](/Manual/UIEditor/Introduction)，并对界面编辑器有一定的了解。

使用星火编辑器创建的游戏需要在电脑、手机、平板等各种终端运行，而它们的宽高比和屏幕分辨率各不相同。在制作游戏UI时，为保证UI在所有分辨率上显示正确且美观，就需要对UI进行自适应适配。

## 各常见设备宽高比及分辨率一览[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#各常见设备宽高比及分辨率一览
"各常见设备宽高比及分辨率一览的直接链接")

设备名| 宽高比| 分辨率  
---|---|---  
PC| 16:9| 1920*1080  
iPhone 15| 19:9| 2556*1179  
iPhone 15 Pro Max| 19:9| 2796*1290  
小米14| 20:9| 2670*1200  
小米14 Pro| 20:9| 3200*1440  
iPad Pro| 4:3| 2732*2048  
  
尽管各设备的分辨率不一定相同，但可以总结出各平台的常用宽高比。其中PC为16:9，平板电脑为4:3，手机主流为19:9/20:9。在星火编辑器中，为了统一各平台的体验，设计分辨率采用2340*1080(宽高比为19.5:9)，运行时根据各平台进行UI适配。

## 基本布局介绍和适配原理[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#基本布局介绍和适配原理
"基本布局介绍和适配原理的直接链接")

本部分会详细介绍UI布局和锚点、缩放、边距等影响布局的属性。

### 布局[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#布局 "布局的直接链接")

![](https://doc.sce.xd.com/assets/images/Layout-cbb05fac5cb8c3f4e25d90be48e07482.png)

布局定义了元素的位置、大小和排列方式。每个UI元素（页面、控件）都有一个矩形外边框。在编辑视图中，可以操作该矩形进行移动、缩放等操作，从而改变布局。

在开启自动布局模式下，控件会根据锚点及相对位置计算最终位置，根据尺寸/扩展权重权重和外边距计算大小；否则，会以父控件左上角为原点，绝对位置为偏移量，确定元素的位置。

外边距和剪裁子控件两个属性为高级属性，需要勾选属性面板中的“显示高级属性”。

### 锚点[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#锚点 "锚点的直接链接")

一个UI元素的锚点是相对父控件的固定点，这个元素的中心到锚点的距离是永恒不变的。锚点类似一根钉子，把一块画布的某个角钉住，无论怎么拉伸，被钉住的这个角都不会变。

![](https://doc.sce.xd.com/assets/images/Anchor-140c6aff55edd9417a2a74243c45f800.gif)

> UI元素锚定到父控件的右上角，与父控件保持固定偏移

假如要做一个右上角的关闭按钮，那么就可以设置锚点为右上，无论面板怎么移动、缩放，这个按钮都会永远保持在右上角，实现了自适应。

### 外边距[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#外边距 "外边距的直接链接")

外边距是UI元素相对父控件的像素距离。边框、外边距、内容关系如图所示：

![](data:image/png;base64,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AIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiLB63AOYBftferHZ962Xxz0MAGAE+77+crN/34vNsWvmxj2UmSNMj5KX953Y3r/yjRPHPBIAYJiKUsZDmB4Fx208Y9xDAABGZKZ0fOwxBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAggjAFACCCMAUAIIIwBQAgwupxD+BI2rt3b7P/mwfGPQwAgGXb/9KLzd5XVzVzc3PjHspRM9VhWk55/ar2fs0JJocBgMlRUTprVh14zbgHAQAAphEBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiCBMAQCIIEwBAIggTAEAiPB/F9Jgk8I7ToQAAAAASUVORK5CYII=)

举例：一个UI元素和父控件大小相同，均为200*200，该控件外边距上下左右均为10，则留给内容的大小为180*180，左上角锚点相当于未添加外边距的(10,
10)位置。

### 尺寸扩展和扩展权重[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#尺寸扩展和扩展权重
"尺寸扩展和扩展权重的直接链接")

在不同分辨率下，仅靠绝对尺寸控制界面或控件的大小是不行的。如果分辨率过小或过大，UI不会根据分辨率进行自动缩放。为了解决这个问题，可以使用尺寸扩展。开启尺寸扩展后，元素的大小由父控件大小和扩展权重决定，可以根据不同分辨率动态调节UI元素的尺寸。

编辑器提供三种扩展权重的方式，如下图和表格所示：

![](https://doc.sce.xd.com/assets/images/ExpandWeight-9776169355c59749c1899ca9f6b46d41.png)

扩展权重| 作用  
---|---  
关| 不扩展，使用实际尺寸  
以宽为基准扩展| 宽度由尺寸扩展权重决定，高度由宽高比决定  
以高为基准扩展| 高度由尺寸扩展权重决定，宽度由宽高比决定  
宽高自主扩展| 宽高都由尺寸扩展权重决定  
  
开启扩展权重后，控件尺寸计算方法为：

  1. 以宽/高为基准扩展：宽/高=父控件宽/高*尺寸扩展权重，另一边为宽/高*宽高比
  2. 宽高自主扩展：宽高都是父控件大小*尺寸扩展权重

注：此处的宽高比为编辑器中宽高比中短边和长边的比值。如宽高比为2:1，则实际宽高比的比值为1/2=0.5

![](https://doc.sce.xd.com/assets/images/ExpandDemo-54f2a47a618a03ee5b2a230bd751c635.gif)

> 示例：锚点为中心，相对位置(0, 0)，以宽为基准扩展，尺寸扩展权重0.5，宽高比2：1，控件会根据大小自动缩放

## UI自适应最佳实践[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#ui自适应最佳实践
"UI自适应最佳实践的直接链接")

在UI制作过程中，一般使用一种标准分辨率（如2340*1080）搭建，完成后切换其他设备的分辨率验证UI适配是否正确。此外，还可以在游戏视图中选择自由比例，通过改变游戏视图的宽高进行UI适配验证。

![](https://doc.sce.xd.com/assets/images/GameResolution-126d593a74a274c34af423c3e440cff3.png)

### 自适应位置方法[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#自适应位置方法
"自适应位置方法的直接链接")

为了使UI能够适配各种分辨率，需要利用锚点辅助定位，用相对位置和扩展尺寸确定位置和大小。

一种将控件保持在屏幕内的办法是：通过改变布局，将控件的位置通过锚点绑定在屏幕四周而不是中央,用相对尺寸确定实际位置。一旦这些控件锚定到各自的角点，无论分辨率或父控件的尺寸如何修改，这些按钮都会固定在对应位置上。

![](https://doc.sce.xd.com/assets/images/AnchorFitExample-88f5ddc89fac252ce973eb20b80e4c6c.png)

> 屏幕左上、右上、正下方分别有三个按钮。左侧为标准分辨率下的状态，当改变分辨率时，不同锚点的适配情况如右图所示

### 自适应尺寸方法[​](/Manual/UIEditor/UIHowTos/AdaptiveDesign#自适应尺寸方法
"自适应尺寸方法的直接链接")

用上述方法适配好位置之后，UI元素会根据屏幕大小自动确定位置。但是由于元素的尺寸是以像素为单位且固定的，当屏幕分辨率过大或过小时，这些元素的尺寸仍然不变，所以占据屏幕的比例会变大或变小，在极端场景下甚至影响用户体验，如图所示：

![](https://doc.sce.xd.com/assets/images/SizeExample-76d713d51708b9b527d28ecb8f1befc9.png)

可以看到，不同分辨率下控件的尺寸各不相同。这种情况下需要开启扩展权重，使用尺寸权重确定相对比例，以保证不同分辨率下用户的视觉感受是一样的。

![](https://doc.sce.xd.com/assets/images/SizeFit1-d0716f6a9a3a5330a1fafbe417fd6971.png)

![](https://doc.sce.xd.com/assets/images/SizeFit2-929a6c259516c9434637dea0dda92255.png)

> 将两个按钮放在一个Panel中，将新创建的Panel和按钮的扩展权重模式设置成以高为基准扩展，并设置对应宽高比，就可以实现根据分辨率按比例缩放。

[上一页案例-阵列](/Manual/UIEditor/UIHowTos/案例-
阵列)[下一页如何用触发修改字体](/Manual/UIEditor/UIHowTos/如何用触发修改字体)


