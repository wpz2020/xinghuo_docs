  * [](/)
  * 创作者中心
  * 开发阶段常用功能
  * 最常用的自定义匹配模式——人数不足时填充AI

复制链接

本页总览

# 最常用的自定义匹配模式——人数不足时填充AI

在实际的使用场景中，最常用的自定义匹配模式是人数不足时填充AI。  
比如「骗骗酒馆」，在匹配进行20s后，若人数不足，则会填充AI来满足开局要求。

##
打开「自定义匹配配置」，创建一个「自由匹配」模板[​](/Manual/Developer/DevStage/AIMatchPattern#打开自定义匹配配置创建一个自由匹配模板
"打开「自定义匹配配置」，创建一个「自由匹配」模板的直接链接")

不懂代码不要怕，往下拉找到两个关键参数：  
`local timeout_lower_bound = 7`  
`local timeout_upper_bound = 9`

默认值为7和9，意思是在匹配进行7s后，若人数不足，则会填充AI来满足开局要求；具体的时间会在7-9s之间随机。  
开发者可以根据自己的实际需求来设定，在匹配玩家不足时填充AI。

然后再找到一行参数：  
`local enable_ai = false`

把这里的布尔值改为`true`，即可开启AI填充。

## 匹配模板中的「AI填充」[​](/Manual/Developer/DevStage/AIMatchPattern#匹配模板中的ai填充
"匹配模板中的「AI填充」的直接链接")

AI填充则是完全的填充AI模式，不进行匹配，将剩余的玩家位置填充AI直接开始。

提示

填充了AI后，进入游戏的具体AI逻辑需要开发者自己写

[上一页如何自定义游戏模式的匹配规则](/Manual/Developer/DevStage/MatchPattern)[下一页如何使用随进随出模式](/Manual/Developer/DevStage/ComeInAndOut)


