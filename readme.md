# 快速上手

## 1.快速编辑

选择多个类似的选项，如城墙城门城墙柱子的hitpoints修改common就会全部编辑

注：可以开多个编辑器实例，也可以直接拷贝别的包的内容，但是高概率导致编辑器崩溃

## 2.善用工具与教程

模组总分类：[《帝国时代 IV》Mod 创意工坊 – Age of Empires 支持](https://support.ageofempires.com/hc/en-us/sections/360012376652-Age-of-Empires-IV-Mod-Workshop)

调整包手册：

https://support.ageofempires.com/hc/en-us/sections/4409121920276-Tuning-Packs

调整包视频详解：[Age of Empires IV Content Editor (1.3): Tuning Packs](https://www.youtube.com/watch?v=GN-4k5ry8S8)



# 模块详解

## 1.abilities模块

**abilities属于编辑器的核心内容之一 (包括游戏内各种单位的技能和效果包，都是在这里定义)**

1. 你可以直接**clone**官方已有的技能包修改(如果是同名技能会自动应用继承)

2. 如果需要引入条件(**requirements**：可用于限定给谁用或者此能力发动需要什么条件)

   需要对应升级类型作为前提而官方没有的，可以先在**upgrade**模块新建或者拷贝已有的进行修改，之后在**abilities**模块将其作为一个技能包组丢出。之后就可以

   A. **abilities**模块的**requirements**里作为**限定条件 **

   B. 可以在**ebps**与**sbps**模块的**ability_ext**的**abilities**里引用(如果需要升级后才能用的科技，记得在**upgrade_ext**里的**standard_upgrades**引入此升级)

   注：

   A 参考 white_stupa_stone_generation_addition 的 **requirements**

   B 参考 ebp 下 **building_town_center_capital_chi** 的 **upgrade_ext** 子类upgrade\races\common\upgrade_empire_rising





简单来说就是你先拟定需要的升级内容，再写能力效果，然后把升级内容作为能力效果的限制写好，最后把此能力分配给实体



4.关于abilities的float_properties

![range](C:\Users\dell\Desktop\aoe4\标准\reinforce_ai_bundle_V2\template(教程)\abilities详解\range.png)

![float property](C:\Users\dell\Desktop\aoe4\标准\reinforce_ai_bundle_V2\template(教程)\abilities详解\float property.png)

3.sbp是修改单位的武器模型以及小队状态，如果想直接修改一个单位类型本身，需要去ebp里的unit修改

## 附录

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

```
城墙减伤
```

``` 
\r\n
石料 x1.5 、金矿 x2
```

```
已应用的修改(0.1.2.1)
联通,朱熹火长矛速度
城墙，长城门楼优先级(未生效)，
添加家园卫士效果(英格兰获得强化城堡网络(强化后变45%，射程+1)，英格兰没家园卫士。蒙古获得强化忽里勒台，蒙古主城只有家园卫士的攻速，蒙古哨塔加强，攻速+)
想法：如果电脑有忽里勒台，检索有没有奇观，有就挪过去旁边，没有就挪到圣地，还没有就挪回自己家部署
```

