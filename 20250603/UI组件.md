  * [](/)
  * 技术文档-使用可视化的开发者请忽略此文档
  * 客户端Lua API
  * UI组件

复制链接

本页总览

# UI组件

👷🛠️  
UI组件提供一种OOP方式来对UI相关逻辑进行封装与管理

## 基本结构[​](/技术文档/客户端Lua API/UI组件/#基本结构 "基本结构的直接链接")

    
    
    local component = require '@common.base.gui.component' -- 提供GUI组件相关特性  
    local ctrl_util = require '@common.base.gui.control_util' -- 提供控件相关实用函数  
      
    local MyComponent = component 'MyComponent' {  
        -- 组件模板定义，可缺省  
        base.ui.panel {  
            -- ...  
            OtherComponent 'part_a' {  
                -- ...  
            },  
            -- ...  
        },  
        -- 组件属性定义，可缺省  
        prop = {  
      
        },  
        -- 组件数据定义，可缺省  
        data = {  
      
        },  
        -- 组件方法定义，可缺省  
        method = {  
      
        },  
        -- 组件事件定义，可缺省  
        event = {  
      
        },  
        -- 组件状态定义，可缺省  
        state = {  
      
        },  
    }  
    

## 相关模块[​](/技术文档/客户端Lua API/UI组件/#相关模块 "相关模块的直接链接")

require 相关模块来引入

  * @common.base.gui.component GUI组件相关特性
  * @common.base.gui.control_util 组件/控件相关的辅助函数，[详见](/技术文档/客户端Lua API/UI组件/#%E8%BE%85%E5%8A%A9%E5%87%BD%E6%95%B0)

    
    
    local component = require '@common.base.gui.component'  
    local new = component.new  
    local destroy = component.destroy  
    local bind = component.bind  
    local getset = component.getset  
    local alias = component.alias  
    local alias_by = component.alias_by  
    local legacy_bind_prop = component.legacy_bind_prop  
    local anim_trans = component.anim_trans  
    local key_frame_state = component.key_frame_state  
      
    local ctrl_util = require '@common.base.gui.control_util'  
    local set_ctrl_prop = ctrl_util.set_ctrl_prop  
    local get_ctrl_prop = ctrl_util.get_ctrl_prop  
    local get_ctrl_type_name = ctrl_util.get_ctrl_type_name  
    local is_ctrl_exists = ctrl_util.is_ctrl_exists  
    local get_final_ext_component = ctrl_util.get_final_ext_component  
    local move_to_new_parent = ctrl_util.move_to_new_parent  
    local is_component_ctrl = ctrl_util.is_component_ctrl  
    

## 内置控件[​](/技术文档/客户端Lua API/UI组件/#内置控件 "内置控件的直接链接")

组件需要基于内置控件来组成，`base.ui.<name>` 都属于[内置控件](/技术文档/客户端Lua API/内置控件/简介)

建议熟悉内置控件的用法后再来使用组件

> 内置控件目前不属于组件，所以不具备组件特性（例如直接通过实例修改属性，内置控件需要通过 set_ctrl_prop
> 设置属性；当然也可不通过实例修改属性，通过 bind表，bind到属性，alias，选择器等也可设置）
    
    
    local A = component {  
        base.ui.panel {  
            bind = {  
                color = 'color',  
            }  
        }  
    }  
    local a = A:new()  
    local ui_panel = a.ui -- 获得组件实例对应的根内置控件    
    a.bind.color = '#ffffff' -- 访问bind对象  
    

## 定义与实例[​](/技术文档/客户端Lua API/UI组件/#定义与实例 "定义与实例的直接链接")

### 组件类型[​](/技术文档/客户端Lua API/UI组件/#组件类型 "组件类型的直接链接")

使用 component 函数进行组件定义，返回组件类型

    
    
    local Com1 = component {  
        -- ...  
    }  
      
    -- 判断组件实例的组件类型  
    local instance_of_com1 = Com1:new()  
    check(instance_of_com1.class == Com1)  
    

### 组件模板[​](/技术文档/客户端Lua API/UI组件/#组件模板 "组件模板的直接链接")

使用 `<组件>{}` 会返回一个组件模板，用来表示一种组成结构

可以在表中填写对属性的修改，或是选择器的设置

> 组件模板不是组件实例，创建模板的过程中也不会创建实例
    
    
    local A = component {  
        prop = {  
            v = 0  
        }  
    }  
    local template = A { -- 创建组件模板  
        v = 123,  
        A {}, -- 子控件  
        -- 模板表里可以写选择字串（详见 选择器）  
        -- 例如:  
        --  ['layout.width'] = 100,  
        --  ['@some_part.foo'] = 'asdfasdf',  
    }  
    

### 实例创建与销毁[​](/技术文档/客户端Lua API/UI组件/#实例创建与销毁 "实例创建与销毁的直接链接")

从组件或组件模板创建其实例

    
    
    local new = component.new  
    local destroy = component.destroy  
      
    local A = component {  
        prop = {  
            v = 0  
        }  
    }  
      
    -- <组件>:new()  
    local a1 = A:new()  
    -- component.new(<组件模板/内置控件模板>)  
    local a2 = new(A{})  
    local a3 = new(A{v = 1})  
    check(a3.v == 1)  
    local panel_ui = new(base.ui.panel{})  
    -- new(A) -- 不支持  
    -- new(base.ui.panel) -- 不支持  
      
    -- <组件实例>:destroy() 销毁组件实例  
    a1:destroy()  
    a2:destroy()  
    -- component.destroy(<组件实例/内置控件实例>)  
    destroy(a3)  
    destroy(panel_ui)  
    

### 实例保留字段[​](/技术文档/客户端Lua API/UI组件/#实例保留字段 "实例保留字段的直接链接")

  * class 所属组件
  * base 基控件
  * part 部件表
  * prop 属性表
  * method 方法表
  * data 数据表
  * child 子控件
  * parent 父控件
  * ui 根内置控件
  * bind 老绑定表
  * state 状态接口
  * connection 事件注册表
  * __开头所有的字段 实现相关

> 不要修改这些字段，否则未定义

## 部件模板[​](/技术文档/客户端Lua API/UI组件/#部件模板 "部件模板的直接链接")

组件定义表的 `[1]` 为该组件的模板定义，用于定义组件的组成部件（part）

    
    
    local C = component {  
        base.ui.panel {  
            color = '#ff00ff',  
            base.ui.button {  
                color = '#ff0000',  
            },  
            OtherComponent {},  
        },  
    }  
    

### 基控件（base）[​](/技术文档/客户端Lua API/UI组件/#基控件base "基控件（base）的直接链接")

组件模板定义的根控件会作为该组件的基，可以理解为继承关系

    
    
    local A = component {  
        -- ...  
    }  
    local B = component {  
        A {  
            -- ...  
        },  
        -- ...  
    }  
    local b = B:new()  
    check(b.base.class == A) -- 通过 base 访问基  
    

### 部件（part）[​](/技术文档/客户端Lua API/UI组件/#部件part "部件（part）的直接链接")

在组件模板定义中，可使用 `<组件/内置控件> '<部件名>' {<...>}` 或 模板属性中的 `name` 作为对应控件的部件名（使用 `name`
的场合，要求定义时必须是字符串，否则行为未定义）。

尽量不使用 `name` 作为部件名，现在允许是因为历史原因，便于迁移

可以认为是在组件定义时为组件的各个组成部分取了一个固定的名称，方便之后逻辑中引用。  
部件名不能动态修改。  
在选择器中以 `@` 引导。

    
    
    local C = component {  
        base.ui.panel { -- 可以通过 <组件实例>.base 获得  
            color = '#ffffff',  
            base.ui.button 'a' {  
            },  
            OtherComponent 'b' {  
                base.ui.label 'c' {  
                },  
            },  
        },  
    }  
      
    local c = C:new()  
    local base_ctrl = c.base  
    check(base_ctrl.color == '#ffffff')  
    local part_c = c.part.c -- 通过 part 得到含有所有部件名为 c 的控件的表  
    check(#part_c == 1)  
    local sub_c = c:select('@c'):get()  
    check(sub_c == part_c[1])  
    

## 子控件（child）与父控件（parent）[​](/技术文档/客户端Lua API/UI组件/#子控件child与父控件parent
"子控件（child）与父控件（parent）的直接链接")

不同于部件，在组件定义外添加到组件实例中的控件称为子，彼此是父子关系

    
    
    local A = component {}  
    local B = component {  
        A {  
            A 'a-1' {},  
            A 'a-2' {  
                A 'a-3' {},  
            },  
        }  
    }  
    local b = B:new()  
    local a_1 = b.part['a-1'][1]  
    local a_2 = b.part['a-2'][1]  
    local a_3 = b.part['a-3'][1]  
    check(#(b.child) == 0)  
    check(#(b.base.child) == 2)  
    check(#(a_1.child) == 0)  
    check(#(a_2.child) == 1)  
    check(#(a_3.child) == 0)  
    check(a_3.parent == a_2)  
    

可通过 `new_child` 方法动态创建子控件，[详见](/技术文档/客户端Lua
API/UI组件/#%E7%BB%84%E4%BB%B6%E7%89%B9%E6%80%A7%E7%9B%B8%E5%85%B3%E6%96%B9%E6%B3%95)

## 子控件插入位置定义[​](/技术文档/客户端Lua API/UI组件/#子控件插入位置定义 "子控件插入位置定义的直接链接")

通过定义 default_child_slot 来指定子控件的插入位置  
通过定义 on_add_child 方法，来对新的子控件实例进行读写  
通过定义 on_new_child 方法，来对将要创建的子控件模板进行预处理

    
    
    local A = component {  
        base.ui.panel {  
            base.ui.panel {  
                component.default_child_slot,  
            }  
        },  
        method = {  
            on_add_child = function(self, ctrl)  
                if ctrl_util.get_ctrl_type_name(ctrl) == 'label' then  
                    ctrl.text = 'Value: '..(ctrl.text or '')  
                end  
            end,  
            on_new_child = function(self, t) -- 若返回值不是模板则不会被创建  
                return t  
            end  
        }  
    }  
    local a = new(A{  
        base.ui.label{  
            text = '1'  
        },  
        base.ui.label{  
            text = '2'  
        },  
    })  
    check(#(a.child) == 2)  
    check(#(a.base.child[1].child) == 2)  
    component.destroy(a.child[1])  
    check(#(a.child) == 1)  
    check(#(a.base.child[1].child) == 1)  
    

## 属性定义[​](/技术文档/客户端Lua API/UI组件/#属性定义 "属性定义的直接链接")

组件定义表的 `prop` 字段为该组件的属性定义

    
    
    local A = component {  
        prop = {  
            a = 1,  
            b = 'b',  
            c = true,  
        },  
        method = {  
            c = function(self)  
                -- ...  
            end  
        }  
    }  
    local a = A:new()  
    check(a.b == 'b') -- 访问属性  
    check(a.prop.b == 'b') -- 通过 prop 访问属性  
    check(type(a.c) == 'function') -- <ctrl>.<key> 会优先访问方法，这时需要通过 prop 来访问 c 属性  
    

### 绑定到属性[​](/技术文档/客户端Lua API/UI组件/#绑定到属性 "绑定到属性的直接链接")

属性可以进行绑定，来同步设置属性的值

> 注意和 bind表 进行区分，bind到属性 与 bind表 没有关系，bind到属性 不依赖 bind表 来实现
    
    
    local A = component {  
        base.ui.panel {  
            base.ui.panel {  
                layout = {  
                    width = bind.width,  
                    height = bind 'height', -- 等价于 bind.height  
                },  
            },  
        },  
        prop = {  
            width = 100,  
            height = 200,  
        }  
    }  
    local a = A:new()  
    a.width = 123  
    

### 属性绑定玩家[​](/技术文档/客户端Lua API/UI组件/#属性绑定玩家 "属性绑定玩家的直接链接")

将控件属性绑定到本地玩家的属性上

    
    
    local on_player_prop = require '@common.base.gui.on_player_prop'  
    local A = component {  
        base.ui.label {  
            text = on_player_prop('金钱')  
        }  
    }  
    local a = A:new()  
    

服务端属性同步方式： [玩家增加属性](/技术文档/客户端Lua API/2_服务端触发/玩家/玩家增加属性.md)
[设置玩家字符型属性](/技术文档/客户端Lua API/2_服务端触发/玩家/设置玩家字符型属性.md) [设置玩家数值型属性](/技术文档/客户端Lua
API/2_服务端触发/玩家/设置玩家数值型属性.md)

    
    
    player:add('金钱', 100)  
    

### alias 转发[​](/技术文档/客户端Lua API/UI组件/#alias-转发 "alias 转发的直接链接")

在组件中创建对应别名属性

    
    
    component {  
        base.ui.panel {  
            base.ui.panel 'inner_panel' {  
                color = alias_by.color,  
                image = alias_by.image,  
            },  
        },  
        prop = {  
            color = '#ff0000', -- 作为别名属性的初值  
            width = alias '@inner_panel.layout.width',  
        	height = alias '@inner_panel.layout.height' (100), -- 100 作为初值  
        }  
    }  
    

### base 转发[​](/技术文档/客户端Lua API/UI组件/#base-转发 "base 转发的直接链接")

读写或绑定未定义的属性，会转发到组件的基控件（base）

    
    
    local A = component {  
        base.ui.panel {  
            color = '#ff00ff',  
            base.ui.button {  
                color = bind.color, -- 由于prop中没有定义 color，会绑定到 base 的 color  
            },  
        },  
        method = {  
            init = function(self)  
                self.color = '#123123' -- 由于prop中没有定义 color，会设置到 base 的 color  
            end  
        }  
    }  
    

### 属性修改事件[​](/技术文档/客户端Lua API/UI组件/#属性修改事件 "属性修改事件的直接链接")

属性被修改后会触发 `on_prop_change_<prop_name>` [事件](/技术文档/客户端Lua
API/UI组件/#%E4%BA%8B%E4%BB%B6)并传播绑定

### 属性类型[​](/技术文档/客户端Lua API/UI组件/#属性类型 "属性类型的直接链接")

属性可以是一般的 lua 类型，或几种特殊的类型

  * getset
    * 提供一种灵活的属性，对属性的读写会对应调用 get 与 set 函数
    * `getset{ get = <function> , set = <function> }`
    * set 返回 true 时会触发属性修改事件与绑定传播，否则不触发
  * alias（别名属性）
    * 转发读写到部件属性，对别名属性进行读写如同对目标属性进行
    * `alias <selector_str>`
  * legacy_bind_prop（用于过渡，应尽量避免使用）
    * 通过该属性进行读写如同对对应的 `self.bind.<bind_name>` 进行
    * `legacy_bind_prop <bind_name>`
  * ！表属性（暂时不要使用，定义属性时不要赋值为表）

    
    
    local B = component {  
        base.ui.panel {  
            base.ui.button 'btn' {  
                color = '#ff0000',  
            },  
        },  
        prop = {  
            v1 = 0,  
            v2 = 'adf',  
            btn_color = alias '@btn.color',  
        },  
        method = {  
            init = function(self)  
                check(self.btn_color == '#ff0000')  
                self.btn_color = '#ff0011' -- 转发到部件名为 btn 的部件的 color 属性  
            end  
        }  
    }  
      
    local A = component {  
        B {  
            -- ...  
        },  
        prop = {  
            v1 = getset {  
                get = function(self) -- 使用 data 存储属性数据  
                    return self.data.v1 or 0  
                end,  
                set = function(self, v)  
                    self.data.v1 = v  
                    print(v)  
                    return true -- 触发属性修改事件与绑定传播  
                end,  
            },  
            color = getset {  
                get = function(self) -- 转发属性  
                    return self.base.color or '#000000'  
                end,  
                set = function(self, v)  
                    if v == nil then  
                        return false  
                    end  
                    if is_component_ctrl(self.base) then  
                        self.base.color = v  
                    else  
                        set_ctrl_prop(self.base, 'color', v)  
                    end  
                    print(v)  
                    return true -- 触发属性修改事件与绑定传播  
                end,  
            }  
        },  
        event = {  
            on_prop_change_color = function(self, v)  
                print('color changed')  
            end  
        }  
    }  
    

## 数据[​](/技术文档/客户端Lua API/UI组件/#数据 "数据的直接链接")

实例创建后可向实例的 `data` 字段读写数据，数据的与一般lua的表一致

    
    
    local A = component {  
        data = { -- 定义data的默认值  
            v1 = 1,  
            v2 = {1,2,3},  
        },  
        method = {  
            init = function(self)  
                self.data.v1 = self.data.v1 + 1  
                self.data.v2[2] = 4  
      
                self.data.any_key = some_obj  
                self.data.layout = { pos = {0,0} }  
            end,  
        }  
    }  
    

## 方法[​](/技术文档/客户端Lua API/UI组件/#方法 "方法的直接链接")

组件定义表的 `method` 字段为该组件的方法定义  
方法是被实例所共享的，一般使用函数

    
    
    local A = component {  
        method = {  
            init = function(self)  
                self:foo(123)  
            end,  
            foo = function(self, v)  
                print(v)  
            end,  
        }  
    }  
    

### 生命周期相关方法[​](/技术文档/客户端Lua API/UI组件/#生命周期相关方法 "生命周期相关方法的直接链接")

一般情况下，应该只覆写，不要在外部显式调用

  * `init(self)` 初始化时调用
  * `update(self, delta_time)` 每帧调用
  * `on_destroy(self)` 销毁时调用

### 组件特性相关方法[​](/技术文档/客户端Lua API/UI组件/#组件特性相关方法 "组件特性相关方法的直接链接")

一般情况下，应该只调用，不要覆写

  * `select(self, selector_str):selector` 根据选择字串在当前控件处构建选择器
  * `emit(self, event_name_str, ...)` 触发组件自定义事件
  * `connect(self, event_name_str, handler):connection` 注册/连接事件响应函数
  * `disconnect(self, connection)` 注销/断开事件响应
  * `destroy(self)` 销毁组件及其子控件
  * `set_state(self, state_name, state_value)` 设置对应状态到指定状态值
  * `get_state(self, state_name):state_value` 返回对应状态的当前状态值
  * `new_child(self, template):ctrl` 根据模板创建子控件并返回

## 事件[​](/技术文档/客户端Lua API/UI组件/#事件 "事件的直接链接")

组件定义表的 `event` 字段为该组件的事件定义  
通过 `emit` 方法进行事件的触发，`connect` 进行事件回调的注册(返回类似触发的对象)  
定义组件自定义事件，可以提供默认处理函数，组件自定义事件是按连接顺序多播的

    
    
    local A = component {  
        base.ui.panel {  
            B 'b' {},  
        },  
        event = {  
            custom_event_without_default_handler = true,  
            custom_event_with_default_handler = function(self, ...) -- 事件参数在 emit 时传入  
                -- ...  
            end,  
            forward_event = '@b:event_of_B', -- 转发事件，对 forward_event 的连接、触发都会转发给 b 的 event_of_B  
        }  
    }  
    local a = A:new()  
    local connection = a:connect('custom_event_without_default_handler', function(self, msg)  
        print(msg)  
    end)  
    a:emit('custom_event_without_default_handler', 'hello world')  
    connection:remove()  
    

### 内置事件[​](/技术文档/客户端Lua API/UI组件/#内置事件 "内置事件的直接链接")

  * `on_prop_change_<prop_name>(self, value)` 对应属性被修改后触发
  * `on_tick(self, delta_time)` （定义后）每帧触发
  * `on_remove(self)` 组件的根内置控件销毁时触发

> 内置事件会被自动定义为 true，除非手动在定义中置为 false

## 状态[​](/技术文档/客户端Lua API/UI组件/#状态 "状态的直接链接")

组件定义表的 `state` 字段为该组件的状态定义  
可以定义多个状态，每个状态有复数个状态值，代表具体所处的状态  
状态初值都为 `nil`，表示未指定，在合适时候通过调用 `set_state` 进行设置  
关键帧状态以 `key_frame_state`
引导，第一个表是一个选择器字符串的数组，表示后面状态数据中各个下标处数据的目标分别是什么。第二个表键为状态值，值为关键帧数据，当进入某个状态值时，数据会设置到对应的目标。  
`anim_trans` 会在进入状态值时进行自定义值动画插值（暂只支持数值的线性插值）。  
`anim_trans` 中的 `time` 属性的单位是毫秒

    
    
    local A = component {  
        -- ...  
          
        state = {  
            my_state = key_frame_state{'b_height', '@a.layout.grow_width'}{  
                [1] = {555, 1.0},  
                active = { anim_trans{time = 4000; 1000, 0.1} }, -- 注意这里外层的 {} 不能缺  
                active_ = { anim_trans{time = 4000; 1000}, anim_trans{time = 2000; 0.1} }, -- 可以单独指定插值  
            },  
            -- ...  
        }  
    }  
    

## 例子[​](/技术文档/客户端Lua API/UI组件/#例子 "例子的直接链接")

    
    
    local component = require '@common.base.gui.component'  
    local bind = component.bind  
    local alias = component.alias  
    local getset = component.getset  
    local legacy_bind_prop = component.legacy_bind_prop  
      
    local MyComponent = component {  
        base.ui.panel 'main' {  
            base.ui.button 'btn' {  
                color = bind 'color', -- 单向绑定到该组件的 color 属性，当该组件的 color 属性被修改，会设置所有绑定到它的属性  
                show = bind.show, -- 另一种格式，与 bind 'show' 等价  
            },  
            base.ui.label {  
                show = bind.show, -- 同一组件属性可以绑定多个目标属性  
            },  
            bind = { -- 老bind格式  
                event = {  
                    on_mouse_down = 'on_mouse_down',  
                },  
                layout = {  
                    height = 'height',  
                },  
            },  
        },  
      
        prop = {  
            color = '#ff0000',  
            show = true,  
            my_prop_0 = 0,  
            my_prop_1 = getset {  
                get = function(self)  
                    return self.data.my_prop_1 or 1  
                end,  
                set = function(self, v)  
                    self.data.my_prop_1 = v  
                    return true -- 返回 true 会派发修改事件与绑定  
                end,  
            },  
            width = alias '@main.layout.width', -- 通过 self.width 进行读写如同对 main 部件的 layout.width 进行  
            height = legacy_bind_prop 'height', -- 通过 self.height 进行读写如同对 self.bind.height 进行  
        },  
      
        event = {  
            custom_event = function(self, v) -- 自定义事件及其默认响应函数  
                print('MyComponent custom_event')  
            end,  
        },  
      
        method = {  
            init = function(self)  
                -- 内置可覆写方法，在该组件lua实例创建成功后被调用  
                  
                -- 调用组件方法  
                self:foo() -- 或 self.foo(self)  
      
                -- 访问组件属性  
                self.width = 100  
      
                -- 使用 self.data 存储或读取组件实例的私有数据  
                self.data.any_value = {0,1,2}  
      
                -- 使用 self.bind 访问老绑定对象  
                self.bind.on_mouse_down = function()  
                    print('MyComponent on_mouse_down')  
                end  
      
                -- 使用 self.ui 访问组件的根内置控件  
                local x, y, w, h = self.ui:rect()  
      
                -- 使用选择器设置部件属性  
                self:select('@btn.layout'):set({width = 100, height = 100})  
      
                -- 使用选择器获取部件  
                local selector = self:select('@btn')  
                local btn_ctrl = selector:get()  
            end,  
            update = function(self, delta_time)  
                -- 内置可覆写方法，每帧调用  
            end,  
            foo = function(self) -- 如果方法名未被占用，则为新的自定义方法，若被占用则为覆写方法  
                -- 使用 self:emit 触发组件的自定义事件  
                self:emit('custom_event', 123)  
            end,  
        },  
    }  
      
    -- 创建组件  
    local com = MyComponent:new()  
    -- 注册事件连接  
    local connection = com:connect('custom_event', function(self, v)  
        print('on_custom_event')  
    end)  
    com:foo()  
    -- 注销事件连接  
    com:disconnect(connection)  
    

## 选择器[​](/技术文档/客户端Lua API/UI组件/#选择器 "选择器的直接链接")

提供一种指代/引用对象的描述  
通过 `select` 方法构造选择器

### 选择器的方法[​](/技术文档/客户端Lua API/UI组件/#选择��器的方法 "选择器的方法的直接链接")

  * get 返回所有符合条件的值
  * set 设置所有符合条件的值

### 目前支持的选择语法[​](/技术文档/客户端Lua API/UI组件/#目前支持的选择语法 "目前支持的选择语法的直接链接")

  * 部件名
    * `@<name>` 读写表示对部件的读写
  * 属性
    * `[<ctrl>.]<prop_name>[.<prop_name>]...` 读写表示对属性的读写
  * 事件
    * `[<ctrl>]:<event_name>` 读写表示对事件连接的获取与注册

    
    
    local ok_btn = component_instance:select('@ok_btn'):get() -- 获取 ok_btn 控件  
    ok_btn = component_instance['@ok_btn'] -- 与上一行等价   
      
    -- 通过 selector 读写属性  
    local prop_selector = component_instance:select('@cancel_btn.color')  
    prop_selector:set('#ff0000')  
    local c = prop_selector:get()  
    -- 上一段的简化方式  
    component_instance['@cancel_btn.color'] = '#ff0000'  
    c = component_instance['@cancel_btn.color']  
    

## 动态改变控件树[​](/技术文档/客户端Lua API/UI组件/#动态改变控件树 "动态改变控件树的直接链接")

  * `move_to_new_parent` 移动控件节点到新的父亲（只影响父子关系，不影响部件关系）
  * 使用部件选择器的 `set` 对部件进行控件替换

    
    
    local ctrl_util = require '@common.base.gui.control_util'  
    local move_to_new_parent = ctrl_util.move_to_new_parent  
      
    -- ...  
      
    local a = A:new()  
    local a_h_selector = a:select('@h')  
    local new_ctrl_template = base.ui.label {  
        text = '物品名称',  
        font = {  
            size = 10,  
            color = '#ffffff',  
        },  
    }  
    local old_h = a_h_selector:get()  
    a_h_selector:set(new_ctrl_template)  
    local new_h = a_h_selector:get()  
    local check_result = new_h ~= old_h and new_h.text == '物品名称'  
    check(check_result, '替换 a 的 h 部件的控件')  
      
    local main = base.ui.map['main']  
    move_to_new_parent(new_h, main)  
    check_result = main.child[#(main.child)] == new_h  
    check(check_result, '从a组件中移到main')  
    

## 继承[​](/技术文档/客户端Lua API/UI组件/#继承 "继承的直接链接")

组件会继承根控件的组件类型，继承内容包括模板，属性，方法，数据，事件，状态

    
    
    local A = component {  
        -- ...  
    }  
    local B = component {  
        A {  
            -- ...  
        },  
        -- ...  
    }  
    

### 会向 base 转发 的一些情况[​](/技术文档/客户端Lua API/UI组件/#会向-base-转发-的一些情况 "会向 base 转发
的一些情况的直接链接")

  * 直接通过 `<组件实例>.<key>` 访问的方法或属性会转发
  * prop 会转发
  * 默认的 update 会转发
  * emit 如果触发的不是自身定义的事件则会转发
  * connect 如果连接的不是自身定义的事件则会转发
  * disconnect 如果注销的连接不是自身定义的事件则会转发
  * get_state 如果不是自身定义的状态则会转发
  * set_state 如果不是自身定义的状态则会转发
  * destroy 会转发

### 获取最终组件实例[​](/技术文档/客户端Lua API/UI组件/#获取最终组件实例 "获取最终组件实例的直接链接")

有的使用需要得到控件的最终组件实例，例如通过内置控件的父子关系得到的永远是内置控件，而这时这个控件可能又是一个组件实例的根控件，我们想要获取这个组件实例，需要通过
get_final_ext_component 获取

    
    
    local A = component{}  
    local ui, bind = base.ui.create(base.ui.panel { A {} })  
    local balabala_ui = ui.child[1]  
    local balabala_ctrl = control_util.get_final_ext_component(balabala_ui)  
    

再有组件父类实例可能想得到子类实例，例如构建一个可覆写的方法

    
    
    local A = component {  
        method = {  
            progress = function(self)  
                -- ...  
                local ret = self:overridable_step()  
                -- ...  
                self:final_step()  
                return ret  
            end,  
            final_step = function()  
                -- ...  
            end,  
            overridable_step = function(self)  
                self = control_util.get_final_ext_component(self)  
                return self:do_step()  
            end,  
            do_step = function(self)  
                return 'A do_step'  
            end  
        },  
    }  
    local B = component {  
        A {},  
        method = {  
            do_step = function(self)  
                return 'B do_step'  
            end,  
        }  
    }  
    local a = A:new()  
    local b = B:new()  
    check(a:progress() == 'A do_step')  
    check(b:progress() == 'B do_step')  
    check(b.base:overridable_step() == 'B do_step')  
    check(b.base.do_step() == 'A do_step')  
    check(b.do_step() == 'B do_step')  
    

## 辅助函数[​](/技术文档/客户端Lua API/UI组件/#辅助函数 "辅助函数的直接链接")

#### `@common.base.gui.control_util`[​](/技术文档/客户端Lua
API/UI组件/#commonbaseguicontrol_util "commonbaseguicontrol_util的直接链接")

ui_ctrl 表示内置控件实例，ctrl 表示内置控件实例或组件实例

  * `get_ctrl_prop(ctrl, prop_name):any` 获取控件属性，prop_name 可以是个数组，例如 `{'layout', 'width'}`
  * `set_ctrl_prop(ctrl, prop_name, value)` 设置控件属性，prop_name 可以是个数组，例如 `{'layout', 'width'}`
  * `get_ctrl_type_name(ctrl):string` 获取控件的类型名字符串
  * `is_component_ctrl(ctrl):bool` 判断是否是组件实例
  * `is_ctrl_exists(ctrl):bool` 判断控件是否存在（创建但未被销毁）
  * `get_final_ext_component(ctrl):ctrl` 获取控件的子类对象（如果没有则返回自己）
  * `move_to_new_parent(ctrl, new_parent_ctrl)` 移动控件到新的父亲

## 实践[​](/技术文档/客户端Lua API/UI组件/#实践 "实践的直接链接")

#### 约定以_开头的属性为私有属性，不作为公开接口对待[​](/技术文档/客户端Lua
API/UI组件/#约定以_开头的属性为私有属性不作为公开接口对待 "约定以_开头的属性为私有属性，不作为公开接口对待的直接链接")

    
    
    local A = component {  
        base.ui.panel {  
            base.ui.panel {  
                color = bind._inner_color, -- 如果 prop 中没有定义 _inner_color, 会绑定到 base 的 _inner_color，如果 base 是内置控件，则会为内置控件创建 _inner_color 属性  
                image = alias_by._image, -- alias_by 不同于 bind, 不存在被 base 的属性取别名的情况，所以会在当前组件自动定义_image属性，若在prop中再定义_image则视为该别名属性的初值  
            }  
        },  
        prop = {  
        -- public  
            v1 = 0,  
      
        -- private  
            _inner_color = '#000000',  
        }  
    }  
    

#### 获取实例进行设置 vs bind 到属性[​](/技术文档/客户端Lua API/UI组件/#获取实例进行设置-vs-bind-到属性
"获取实例进行设置 vs bind 到属性的直接链接")

如果可以简单的获取实例进行设置，则不使用bind到属性，这可以省去一个属性及其绑定相关的消耗

#### alias属性 vs bind到属性[​](/技术文档/客户端Lua API/UI组件/#alias属性-vs-bind到属性 "alias属性
vs bind到属性的直接链接")

alias属性不会存储数据，只是将设置与获取转发给了目标属性，通过alias属性获取的值是当前目标属性的值。alias原则上是一对一的关系，不建议出现一个别名多个目标的情况（这时你可能需要bind）

bind是属性被设置后同步数据的指定，当属性被修改后会向所有同步派发修改后的属性值（alias属性也会执行该逻辑）

#### 参数化生成组件[​](/技术文档/客户端Lua API/UI组件/#参数化生成组件 "参数化生成组件的直接链接")

    
    
    local function btn(is_switch)  
        return component {  
            base.ui.panel {  
            },  
        }  
    end  
    local SwitchButton = btn(true)  
    local Button = btn(false)  
    

#### 内置控件的一些问题[​](/技术文档/客户端Lua API/UI组件/#内置控件的一些问题 "内置控件的一些问题的直接链接")

1 event、layout 等内置表属性的子项赋值，要使用 选择器 或 set_ctrl_prop 2 内置控件创建时 `static = false`
或 event 属性有初值，事件才能起作用  
3 内置控件 panel 使用 array 属性时，不能使用 ”bind到属性“ 对子控件属性进行修改（属性只会对绑定的属性同步自己的值），要使用
bind/part/child 进行读写

[上一页过渡](/技术文档/客户端Lua API/内置控件/过渡)[下一页单位](/技术文档/客户端Lua API/单位/单位)


