  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 服务端Lua API
  * 如果没用过Lua

复制链接

本页总览

# 如果没用过Lua

本文假设你有其它语言的基础（如C++）但不了解Lua，想要快速地了解以下

常规语法就不介绍了，主要列了些Lua和其它语言的不同，和一些其它注意事项

## 语法快速测试[​](/技术文档/服务端Lua API/如果没用过Lua#语法快速测试 "语法快速测试的直接链接")

对lua语法不明确的，可以在这儿`https://www.lua.org/cgi-
bin/demo`文本框里直接跑一下。引擎对lua作了少量的修改，即有少量情况lua官网跑lua的结果和我们引擎跑的结果会不同。

## 动态类型[​](/技术文档/服务端Lua API/如果没用过Lua#动态类型 "动态类型的直接链接")

这几乎是脚本语言的共同特点。即你拿到一个变量，不一定就是你认为的那个类型，他可能在不同的情况下有不同的类型。如果不确定一个变量的类型，可以用type来判断：

    
    
        if type(value) == 'table' then  
            -- do something  
        end  
    

## 多返回值[​](/技术文档/服务端Lua API/如果没用过Lua#多返回值 "多返回值的直接链接")

函数可以返回多个返回值。如果你用的地方不想要多个，你可以丢弃后面的变量(Python这么写的话会报错)。例如：

    
    
        local function get_unit_info()  
            --- do something  
            return hp, mp, attack, defense  
        end  
        local unit_hp, unit_mp = get_unit_info()  
    

## table[​](/技术文档/服务端Lua API/如果没用过Lua#table "table的直接链接")

在lua里，数组和哈希表都是table。或者你可以理解为，一个lua的table同时包含了一个数组和一个哈希表，只不过我们通常不会同时使用table的数组和哈希表功能。

table作为数组的话，下标从1开始，通常用ipairs遍历，用数字下标读写。用#返回长度。注意长度的定义是从下标1开始，直到遇到nil，看有多少个元素。

    
    
        for i, x in ipairs(t) do  
            -- i是下标, x是内容  
        end  
      
        local t2 = {}  
        t2[2] = 1  
        print(#t2) -- 输出0，因为下标1是nil。这时候如果用ipairs遍历，也是遍历不出东西的。  
        t2[1] = 3  
        print(#t2) -- 输出2。另外要注意如果数组里元素很多，那么得避免频繁使用#，因为table取长度的操作不是O(1)的  
    

table作为哈希表的话，用pairs遍历。pairs会遍历table的所有内容，包括ipairs的。即pairs的结果包含ipairs。用ipairs合适的地方应优先使用ipairs，效率高些(不过我没实际测试过)

    
    
        for x in pairs(t) do  
            -- x是内容  
        end  
    

## 闭包[​](/技术文档/服务端Lua API/如果没用过Lua#闭包 "闭包的直接链接")

闭包的概念不少语言都有，不过C/C++没有。以下是官方文档的个例子：

    
    
        function newCounter ()  
            local i = 0  
            return function ()   -- 匿名函数  
                i = i + 1  
                return i  
            end  
        end  
          
        c1 = newCounter()  
        print(c1())  --> 1  
        print(c1())  --> 2  
    

闭包(closure)就是一个函数加上所有他需要访问到的上值(upvalue)。上面的例子里i就是上值。如果接着上面的例子再写两行：

    
    
        c2 = newCounter()  
        print(c2())  --> 1  
        print(c1())  --> 3  
        print(c2())  --> 2  
    

可以看到，再次调`newCounter()`又产生了个新的闭包，彼此的上值是独立的

## 语法糖[​](/技术文档/服务端Lua API/如果�没用过Lua#语法糖 "语法糖的直接链接")

就是一些简写代码的方式.. 有时候会坑不熟悉Lua的人。常用的几个:

如果只有一个参数，且该参数是字符串或table，那么可以省略括号，如`print 'hi'`其实就是`print('hi')`

    
    
        attack:add_damage  
        {  
            source = source,  
            target = target,  
            damage = 100,  
        }  
      
        -- 上下两段代码其实是一个意思  
        attack:add_damage(  
        {  
            source = source,  
            target = target,  
            damage = 100,  
        }  
        )  
      
    

再看这一段:

    
    
        unit2:play_animation '开枪'  
        {  
            speed = 1.0,  
            loop = false,  
            part = 1  
        }  
      
        -- 完整的写法：  
        unit2:play_animation('开枪') (  
        {  
            speed = 1.0,  
            loop = false,  
            part = 1  
        })  
        -- 也就是说，unit2:play_animation('开枪') 返回了一个方法(其实是个带上值的闭包)，然后我们给这个方法传了一个table参数  
    

另一个常见坑：

    
    
    local tb = {}  
    function tb:getName1()  
        print(self) -- table: xxxxxxx(地址)  
    end  
      
    function tb.getName2()  
        print(self) -- nil  
    end  
    

用:的话，相当于把冒号前面的变量作为self传给方法。注意现在我们封装的api，有的用的是冒号，有的用的是点，别弄错了..

另外，table的下标如果是常量字符串，可以直接用点访问。即`a.x = 10`等价于`a["x"] = 10`

## 元表[​](/技术文档/服务端Lua API/如果没用过Lua#元表 "元表的直接链接")

table可以定义一些元方法，用C++的说法，可以近似的理解为可以重载这些元方法。需要具体了解的再自己搜一下

## 多行字符串[​](/技术文档/服务端Lua API/如果没用过Lua#多行字符串 "多行字符串的直接链接")

    
    
    local str = [[  
        hello  
        world  
    ]]  
      
    local str2 = [==[  
        this is also  
        a multiline string  
        开始的时候带几个等号，结束的时候也带几个等号  
        有时候我们也拿多行字符串当多行注释用，因为Lua似乎没有多行注释？  
    ]==]  
    

## and 和 or[​](/技术文档/服务端Lua API/如果没用过Lua#and-和-or "and 和 or的直接链接")

a and b -- 如果a 为false，则返回a，否则返回b

a or b -- 如果a 为true，则返回a，否则返回b

<https://blog.csdn.net/heyuchang666/article/details/51005550>

所以可以用`a and b or c`来实现c语言里`a ? b : c`的效果

[上一页我们对Lua做的修改](/技术文档/服务端Lua API/我们对Lua做的修改)[下一页单位属性](/技术文档/服务端Lua
API/单位/单位属性)


