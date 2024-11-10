1.快速编辑

选择多个类似的选项，如城墙城门城墙柱子的hitpoints修改common就会全部编辑

注：可以开多个编辑器实例，也可以直接拷贝别的包的内容，但是高概率导致编辑器崩溃

2.新建技能模块
先在upgrade模块新建或者拷贝已有的进行修改，之后在abilities模块将其作为一个技能包组丢出，然后就可以在ebps或sbps模块的ability_ext的abilities里引用(如果需要升级后才能用的科技，记得在upgrade_ext里的standard_upgrades引入此升级)

简单来说就是你先拟定需要的升级内容，再写能力效果，然后把升级内容作为能力效果的限制写好，最后把此能力分配给实体

```
关注参数(基本共通)：
help_text_formatter(功能描述文本)
screen_name(此功能的名字)
ui_position(图标展示所在网格菜单的位置)
upgrade_type(升级类型 貌似用于算科技总分的)
owner_type(属于谁的)
time_cost(成本设置：时间，资源)
requirements(条件所需 可以在此设置前置条件)
```

ebps字段

```
time_seconds 建造时间
hitpoints 生命值
```

未确定

```
城墙减伤
```

``` 
\r\n
石料 x1.5 、金矿 x2
```

