---
title:  "[宠物PLUS]BerryPetPlus"
mathjax: true
layout: post
categories: media
---



**一款简单方便、功能强大的宠物插件！！**

---

# 插件简介
**兼容spigot、paper、cat端！**

1. 宠物能够攻击！宠物能够识别主人当前正在攻击的目标，并协同作战！
2. 全部配置公式化！包括但不限于宠物的攻击伤害、攻击间隔、升级所需经验……全部都能与宠物等级挂钩！
3. 宠物能够升级培养！通过多种方式获得宠物经验，升级你的宠物，从而结合公式化的配置来增加属性！
4. 宠物能够为主人提供属性加成！同样支持公式化计算！
5. 宠物能够释放技能！对接MythicMobs的技能，能够让宠物释放技能，或者让主人释放MM技能！
6. 技能触发器多样！包含多种技能触发方式，左键/右键/攻击时触发/受伤时触发/按键触发/循环触发/宠物攻击触发/宠物受伤触发/宠物生成触发/宠物死亡触发。
7. 支持多种属性插件！AP 2.x/3.x、SX 2.x/3.x、ILO、PxRpg、AS、OA
8. 支持宠物不同等级不同名字、从而配合模型做到进化等操作！
9. 完美支持DragonCore/GermPlugin槽位及模型动作！
10. 宠物自带生命系统！包含宠物口粮系统！
11. 宠物可以识别属性插件的属性！！！
12. [已上线]宠物装备系统！给宠物增加装备吧！

---

# 开始使用
**购买插件**
**请找作者草莓：qq 2332742172 购买！**
**原价260、发售初期打折180！**
**原BerryPet用户免费更新！**
**拥有其他插件的老用户以及一次性打包多个插件的用户折扣更多！**
**前置插件**

1. **[必备]**MythicMobs 推荐4.7.2及以上版本
2. **[必备]**BerryLib 最新版
3. **[必备]**AttributeCompatibleAPI 最新版**(群文件下载)**
4. **[二选一]**DragonCore(龙核) 或者 GermPlugin(萌芽)
5. 任选一个支持的属性插件

**售后群操作**

1. 在购买了BerryPetPlus插件后，在群内输入 `list` 查看自己是否已经拥有该插件，没有请找草莓为您添加。
2. 在售后群输入 `download` 指令，获得最新版的BerryLib下载地址，点击下载。
3. 在售后群输入 `unbind` 指令，解绑一次，这样开服时便会自动绑定ip，同理以后服务器ip变动也要输入。
4. 将BerryLib放入服务端的plugins文件夹，启动服务器，待生成BerryLib文件夹后，关闭服务器。
5. 在BerryLib文件夹中的config.yml文件中，填写您的QQ和插件名字，例如下面这样：

```yaml
#您购买的qq号
qq: '您购买的qq号'

plugins:
  - 'BerryPetPlus'

```

6. **[注意]在BerryLib文件夹下的BerryPetPlus文件夹中，config.yml文件中修改您的数据库设置，并选择是萌芽还是龙核！(因为这两项更改后需要重启一下，所以建议先更改再开服)**
  
```yaml
#存储玩家宠物物品的数据库
#更改请重启!
database:
  host: localhost
  port: 3306
  user: user
  password: password
  database: database
  table: table
  #true为MySQL false为本地SQLite
  enable: false

#插件设置
#有2种设置
#1代表龙核 一切沿用龙核
#2代表萌芽 一切沿用萌芽
#更改请重启
state: 1
```

7. 开启服务器，云端将会自动下载插件到您的服务器并加载，现在，开始使用！

---

# 配置宠物槽位
在 `**BerryLib/BerryPetPlus/slots.yml**` 文件中，配置宠物槽位的设置，如下配置文件，参考注释

```yaml
#如果您是龙核用户：请 不要在 龙核的SlotConfig.yml中填写宠物槽位的注册信息!
  #因为本插件自己保存槽位物品，请一定不要在SlotConfig.yml中再去注册一边槽位！
  #在SlotConfig.yml中注册的槽位，龙核会管理其物品存储，这与本插件是冲突的！
  #并且为了防止属性重复增加，请不要给宠物槽位开启读取物品属性的操作！本插件自己加属性，宠物物品上Lore显示的属性仅仅是给玩家看的！
#如果您是萌芽用户：请 不要将 槽位名字填写为以 germplugin_ 开头的identity！
  #同理，对于 germplugin_ 开头的槽位id，萌芽插件会管理其物品存储，这与本插件冲突！
  #并且为了防止属性重复增加，请不要给宠物槽位开启读取物品属性的操作！本插件自己加属性，宠物物品上Lore显示的属性仅仅是给玩家看的！

#请先提前在config设置插件类型 龙核/萌芽
#识别的槽位设置
#宠物槽位: 将宠物物品放到下面槽位即可召唤
#格式
#槽位id;如果需要设置为按键召唤,这里填写按键
#不写按键id的话则是放入就召唤，拿出就取消召唤
#写按键id就是按一下召唤，按一下不召唤
#萌芽键位见 http://wiki.germmc.com/turtorial/keycode.html?h=key
#例如 KEY_H
slots:
  - '宠物_槽位;H'
  - '宠物_槽位2'

#按键召唤的冷却
#避免频繁召唤/撤销宠物造成问题
#单位：s
cooldown: 10

```

## [注意]
**如果您是龙核用户：**请 **不要在 **龙核的SlotConfig.yml中填写宠物槽位的注册信息，因为本插件自己保存槽位物品，请**一定不要在SlotConfig.yml中再去注册一边槽位**！在SlotConfig.yml中注册的槽位，龙核会管理其物品存储，这与本插件是冲突的！并且为了防止属性重复增加，请不要给宠物槽位开启读取物品属性的操作！本插件自己加属性，宠物物品上Lore显示的属性仅仅是给玩家看的！
**如果您是萌芽用户：**请 **不要将 **槽位名字填写为以 `**germplugin_**` 开头的identity！同理，对于 `**germplugin_**` 开头的槽位id，萌芽插件会管理其物品存储，这与本插件冲突！并且为了防止属性重复增加，请不要给宠物槽位开启读取物品属性的操作！本插件自己加属性，宠物物品上Lore显示的属性仅仅是给玩家看的！

---

# 配置宠物
在 `**BerryLib/BerryPetPlus/pets**` 文件夹下，有一个 `**example.yml**` 文件，为**示例宠物配置**。
文件名**去掉后缀.yml**之后，便是宠物的内部id，请不要重复！(例如 `**example.yml**` 对应的就是id为 `**example**` 的宠物)
每个节点均有详细的配置注释，参考文件注释即可！
提示：宠物属性部分的移动速度别写太快了，要不然很鬼畜

```yaml
#文件名字为宠物id
#配置中除了type节点一定要填写以外 其他的都可以不填写 直接删除整个节点即可(包括节点名字)

#宠物获得经验的方式
#1、经验丹 详见exp.yml文件
#2、在MM怪物中的Drops配置项下配置掉落 格式如下
#Drops:
#  - petexp 10-20 0.5
# 10-20是经验数目 随机区间 也可以直接写一个固定数字 必须是整数
# 后面的 0.5 是掉落概率 0-1之间即可

#----------------------------------------------------------------------------------------------

#宠物基本设置
#基本设置中的全部节点都不可删除!必须填写!
pet-basic-data:

  #宠物物品设置
  bind-item:
    #物品材质 全英文大写
    #注意！！！！不要让该材质的物品能叠加放！否则可能会造成bug 最好是唱片啥的，最好不要让他叠加
    type: 'PAPER'
    #如果是头颅 在这里填写skinValue
    #例如eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZDE3MTU3ZjNkYzNlMWE1OTJiNDNiNGVmN2UxNjg3OTRlYzYyNzEzOGExMDY1MzcyM2FkMzJjOGQxNjAyNiJ9fX0
    #可以在网站 https://minecraft-heads.com/ 查看
    #不需要的话请删除该节点！！！
    skinValue: ''
    #物品展示名
    name: '&b测试宠物'
    #物品lore 支持替换符 {0}当前等级   {1}最大等级 {2}当前经验 {3}下一级所需经验
    #lore只是用来给玩家看的 不起加属性的作用 请关闭宠物/宠物装备槽位的加属性功能
    lore:
      - '&b-----宠物物品-----'
      - '&a当前等级: {0}/{1}'
      - '&a当前经验: {2}/{3}'
      - '&a增加攻击: 10 * {0}'
      - '&b其他写法: #level * 10# 这中间会被替换为公式并计算,level代表宠物等级'

  #宠物名字
  #支持papi解析 {0}代表宠物等级 {1}代表当前经验 {2}代表下一级经验 {3}代表宠物的最大等级
  pet-name: '测试宠物 owned by %player_name% 当前等级:{0}/{3} 当前经验:{1}/{2}'

#----------------------------------------------------------------------------------------------

#宠物属性部分
#宠物的自身属性
pet-attribute:

  #攻击
  #支持公式和papi 加减乘除括号
  #level代表宠物当前等级
  attack: 'level * 5'
  #移动速度
  #支持公式和papi 加减乘除括号
  #level代表宠物当前等级
  speed: 'level + 1'

  #宠物攻速
  #以tick为单位 20tick=1s
  #多少tick一次
  interval: '20'


#----------------------------------------------------------------------------------------------


#宠物属性加成部分
#宠物加成给主人的属性
#两种类型都有效
#属性名;值(支持公式--四则运算)(level 宠物当前等级)
#支持PAPI 前提是这个PAPI必须返回一个数字！！！
#对于PxRpg,属性格式如下
#属性名;最小值(支持公式--四则运算)(level 当前等级);最大值(支持公式--四则运算)(level 当前等级);是否为百分比加成?true代表是,false代表不是
pet-add-attribute:
  - '物理伤害;(level + 100)/5'
  - '生命力;(level + 10)*10'
  #px
  #- '物理伤害;(level + 100)/5;(level + 100)/2;true'

#----------------------------------------------------------------------------------------------

#宠物等级设置
level-settings:
  #最大等级
  max-level: 100
  #升级所需经验 宠物初始等级为1级 此为公式 level 变量代表当前等级 四则运算即可
  up-need: 'level + 100'
  #宠物每级设置
  #当宠物到达x级时，触发y
  every-level:
    #例如 当宠物到达2级时
    2:
      #该阶段的名字(不需要直接删除该name节点即可)
      #支持papi解析 {0}代表宠物等级 {1}代表当前经验 {2}代表下一级经验 {3}代表宠物的最大等级
      name: '测试宠物2 %player_name% &aLv2'
      #触发以下脚本 kt(不需要直接删除该scripts节点即可)
      scripts: |
        tell "宠物到达2级!形态2!"
    20:
      scripts: |
        tell "宠物到达20级!形态3!"

#----------------------------------------------------------------------------------------------

#宠物技能设置
  #支持 mythicmobs技能
  #有以下的触发方式
  #LEFT 宠物主人左键 触发技能
  #RIGHT 宠物主人右键(右键触发必须手上拿的有东西!!!!!!或者右键方块) 触发技能
  #TICK;时间 宠物出战期间,每多少秒触发一次
  #HURT;几率(0-1) 当主人受到攻击时,有多少几率触发该技能
  #DAMAGE;几率(0-1) 当主人造成伤害时,有多少几率触发该技能
  #SLOT1;键位 当宠物放到龙核槽位时 按下键位对应的键触发 例如 SLOT1;H 就是按下H键触发
  #SLOT2;键位 当宠物放到萌芽槽位时 按下键位对应的键触发 例如 SLOT2;KEY_H 也就是H键触发
  #萌芽键位见 http://wiki.germmc.com/turtorial/keycode.html?h=key

pet-skills:
  #技能内部id 不重复即可
  s1:
    #填true代表宠物执行这个技能 填false代表主人执行这个技能
    #仅对于下面的mm技能来说的 如果填true代表下面的mm技能是宠物去发出的 如果填false则说明下面的mm技能是玩家发出的
    is-pet-self: true
    #技能正在冷却时的冷却信息提示，删除则为不提示
    #{0}代表剩余秒数
    show-info: '宠物技能正在冷却! 剩余{0}s'
    #技能冷却(s)
    #支持PAPI参与计算 level代表宠物等级
    cool-down: '10 - (level * 0.5)'
    #需要宠物最低多少级才会触发
    level: 2
    #宠物大于多少级就不能触发了
    max-level: 20
    #触发的类型 见上
    type: 'LEFT'
    #触发的 mythicmobs 技能id
    skill-id:
      - 'sk1'
      - 'sk2'
    #触发的kt脚本
    #kt脚本;冷却(s)
    kts: |
      tell *"释放技能1!"
    #触发增加的属性
    #支持PAPI 前提是这个PAPI必须返回一个数字！！！
    #物理伤害;数值(支持公式--四则运算)(level 当前等级);持续时间(s);
    #对于PxRpg
    #属性名;最小值(支持公式--四则运算)(level 当前等级);最大值(支持公式--四则运算)(level 当前等级);是否为百分比加成?true代表是,false代表不是;持续时间(s)
    add-attribute:
      - '物理伤害;level*100;20'
  s2:
    is-pet-self: true
    cool-down: 19
    level: 5
    max-level: 20
    type: 'ATTACK'
    skill-id:
      - 'test1'
    kts: |
      tell *"释放技能2!"
    add-attribute:
      - '生命力;level*100;20'

```

---

# 宠物获取经验的方式
宠物获取经验的方式有三种：

1. 通过指令给予，详见指令章节。
2. 通过经验丹给予，详见[经验丹章节](#rJkyy)。
3. 通过配置MythicMobs的掉落，从而实现玩家击杀MM怪物时，给宠物经验，详见[MythicMobs适配章节](#lh3fx)。
## 经验丹
在配置文件 `**exp.yml**` 中，配置全部的经验丹设置。
经验丹使用方法为：**将经验丹放在副手 宠物物品拿在主手 然后右键即可使用经验丹**
更多介绍详见 `**exp.yml**` 的注释

```yaml
#经验丹是宠物获得经验的一种玩法
#只识别物品名字 全匹配则认作经验丹
#将经验丹放在副手 宠物物品拿在主手 然后右键即可使用经验丹

#宠物获得经验的方式
#1、经验丹 详见exp.yml文件
#2、在MM怪物中的Drops配置项下配置掉落 格式如下
#Drops:
#  - petexp 10-20 0.5
# 10-20是经验数目 随机区间 也可以直接写一个固定数字 必须是整数
# 后面的 0.5 是掉落概率 0-1之间即可

#本配置文件配置经验丹
exp:

  #经验丹id(不可重复)
  id1:
    #识别的物品的名字
    #全匹配包括颜色
    name: '&a初级宠物经验丹'
    #加的经验数目
    #支持计算公式 支持PAPI level代表宠物当前等级 nowexp代表宠物当前经验 nextexp代表宠物升到下一级所需要的经验
    #例如 nextexp * 0.5 就是增加升级所需要的经验的50%
    add: '10'

    #直升加的等级数目
    #同理支持公式
    #不需要的节点可以删除
    add-level: '10'

    #经验丹限制
    #可以使用该经验丹的最小等级
    min-level: 0
    #可以使用该经验丹的最高等级
    max-level: 20
    #可以使用该经验丹的宠物的id
    #不写该节点则默认全部宠物都可以使用
    can-use-pets:
      - 'example'

  id2:
    name: '&b中级宠物经验丹'
    add: 'nextexp * 0.5'
    min-level: 10
    max-level: 100

  #也可以写直接加等级的经验丹
  id3:
    name: '&b宠物直升20级丹'
    add-level: '20'
    min-level: 10
    max-level: 100

```

---

## MythicMobs适配

1. 给怪物的Drops节点中增加如下配置，能让怪物在被杀死时为全部槽位的宠物增加经验

```yaml
Drops:
  - petexp 10-20 0.5
# 10-20是经验数目 随机区间 也可以直接写一个固定数字 必须是整数
# 后面的 0.5 是掉落概率 0-1之间即可

```

1. 宠物技能直接识别MythicMobs的技能ID

---

# 插件指令
插件指令前缀有：

1. berrypetplus
2. pet2
3. bpetp

**全部指令可Tab补全**
**[]内的东西代表可选内容**
## reload
/pet2 reload
重载全部配置(除了config.yml中提到的两个必须重启的配置)
## getItem
/pet2 getItem 宠物内部id [玩家id(默认为自己)] [数量(默认为1)]
给予指定玩家指定数量的，指定id的宠物的初始物品
## addexp
/pet2 addexp 宠物槽位名字 数目 [玩家id(默认为自己)]
给指定玩家指定宠物槽位的宠物增加一定数量的经验值
## addlevel
/pet2 addlevel 宠物槽位名字 数目 [玩家id(默认为自己)]
给指定玩家指定宠物槽位的宠物增加一定数量的等级

---

# 插件PAPI
```
插件变量
变量开头为 berrypetplus
  %berrypetplus_name:宠物槽位id% 对应槽位上宠物的名字
  %berrypetplus_nowlevel:宠物槽位id% 对应槽位上宠物的当前等级
  %berrypetplus_maxlevel:宠物槽位id% 对应槽位上宠物的最大等级
  %berrypetplus_nowexp:宠物槽位id% 对应槽位上宠物的当前经验
  %berrypetplus_nextexp:宠物槽位id% 对应槽位上宠物的升到下一级需要的经验
  %berrypetplus_health:宠物槽位id% 对应槽位上宠物的当前血量
  %berrypetplus_maxhealth:宠物槽位id% 对应槽位上宠物的最大血量
```

---

# 更新记录
2023-2-1重大更新！！！
1、宠物的pet-attribute节点增加许多节点，具体用途见注释，这些节点均可自由加入，复制下面的即可。

```yaml
#宠物属性部分
#宠物的自身属性
pet-attribute:

  #宠物是否为无敌的？
  #不写该节点则默认无敌
  #true 代表无敌 宠物无法受到任何伤害
  #false 则代表不无敌 宠物会被攻击且会死亡 死亡后经过一段时间则会自动重生
  is-invulnerable: false

  #宠物的生命
  #支持公式和papi 加减乘除括号
  #level代表宠物当前等级
  health: 'level + 10'

  #宠物免疫的伤害类型
  #CONTACT, ENTITY_ATTACK, ENTITY_SWEEP_ATTACK, PROJECTILE, SUFFOCATION, FALL, FIRE, FIRE_TICK, MELTING, LAVA, DROWNING, BLOCK_EXPLOSION, ENTITY_EXPLOSION, VOID, LIGHTNING, SUICIDE, STARVATION, POISON, MAGIC, WITHER, FALLING_BLOCK, THORNS, DRAGON_BREATH, CUSTOM, FLY_INTO_WALL, HOT_FLOOR, CRAMMING, DRYOUT, FREEZE;
  #参考链接 https://helpch.at/docs/1.12.2/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html
  #例如FALL就是跌落伤害 意思就是宠物不会受到跌落伤害
  #其他意思请自行翻译
  no-damage:
    - 'FALL'

  #可以给宠物增加来自于属性插件的属性
  #例如AttributePlus3.x
  #同理 也支持papi 支持level替换为宠物当前等级
  #属性名;值(支持公式--四则运算)(level 宠物当前等级);跟在最后面的符号，例如ap3要读取百分比的话就是在最后加一个 (%)
  #支持PAPI 前提是这个PAPI必须返回一个数字！！！
  #对于PxRpg,属性格式如下
  #属性名;最小值(支持公式--四则运算)(level 当前等级);最大值(支持公式--四则运算)(level 当前等级);是否为百分比加成?true代表是,false代表不是
  attributes:
    - '物理伤害;level * 5'
    - '物理伤害;5;(%)'


  #宠物能否攻击？
  #不写该节点则默认为true
  can-attack: true

  #攻击
  #支持公式和papi 加减乘除括号
  #level代表宠物当前等级
  attack: 'level * 5'

  #移动速度
  #支持公式和papi 加减乘除括号
  #level代表宠物当前等级
  #不建议该值随等级增大而增大 一般来说0.8左右即为正常的移动速度 太快会鬼畜
  speed: 'level + 1'

  #宠物攻速
  #以tick为单位 20tick=1s
  #多少tick一次
  interval: '20'

  #宠物拾取物品设置
  #当开启之后 宠物每隔一段时间便会拾取身边的掉落物直接加入到主人的背包中，如果背包满了则不行
  pickup:
    #是否开启？
    enable: false
    #拾取半径
    #支持公式和papi 加减乘除括号
    #level代表宠物当前等级
    range: 'level + 1'
    #拾取间隔(单位 秒)
    #支持公式和papi 加减乘除括号
    #level代表宠物当前等级
    period: 'level + 1'
```
2、宠物支持了属性插件的属性，能够为宠物增加属性插件的属性！在宠物配置文件的pet-attribute节点下的attributes节点配置即可（见上，无该节点请自行添加该节点）
3、宠物加入生命系统！见上新增节点中的health节点和is-invulnerable节点注释。
4、宠物技能新增技能触发器
```yaml
PETATTACK 当宠物自己攻击时 触发的技能
PETHURT 当宠物自己受到伤害时 触发的技能
PETDEATH 当宠物死亡时 触发的技能
PETSPAWN 当宠物生成时 触发的技能(第一次召唤和重生均会触发)
```
5、宠物技能新增节点 rate 概率节点，用来设置宠物技能触发的概率，自行添加该节点即可。
```yaml
pet-skills:
  #技能内部id 不重复即可
  s1:
    #新增 技能触发的概率
    #不写默认为100%
    #支持计算 level代表宠物等级 也可以写papi 前提是papi返回一个数字！
    #0-1 0.1代表10%
    rate: '0.5 + (level * 0.1)'
```
6、新增PAPI
  %berrypetplus_health:宠物槽位id% 对应槽位上宠物的当前血量
  %berrypetplus_maxhealth:宠物槽位id% 对应槽位上宠物的最大血量
7、config新增设置，其中，打开addNoSpawn节点则可以让按键宠物即使在未按键生成实体时，只要放在了槽位上就可以加属性。
```yaml
#当获取宠物变量失败时展示的文字
info: '[宠物系统]错误的变量'

#对于按键召唤的宠物 当没生成宠物实体是，是否增加属性？
addNoSpawn: false

#宠物的一些设置

#1、宠物是否会攻击玩家？例如当玩家PVP时，宠物是否会攻击对方玩家？
can-attack-player: false

#2、宠物是否会攻击其他宠物实体？当自己的主人攻击到了其他人的宠物时，自己的宠物是否会去一起攻击？
can-attack-other-pet: false
```
8、新增宠物口粮系统！为宠物喂食口粮可以回复其血量！请更新至最新BerryLib，将会自动生成（如果没有可以复制下面的内容，自行在BerryPetPlus文件夹下创建petfood.yml文件）
```yaml
#本文件配置宠物的食物
#副手拿宠物食物 主手拿宠物物品
#右键即可进行喂食
#喂食会回复宠物血量
#当宠物血量为0时将无法召唤助战和加成属性
#识别食物只需名字一致即可 包括颜色

food:

  #id 不重复即可
  id1:
    #识别物品名字
    name: '初级宠物口粮'
    
    #回复的血量
    #支持计算公式 支持PAPI
    #level代表宠物当前等级 nowexp代表宠物当前经验 nextexp代表宠物升到下一级所需要的经验 maxhealth代表宠物的最大血量 health代表宠物当前血量
    regen: '10'
    
    #使用口粮的等级限制
    #可以使用该口粮的最小等级
    min-level: 0
    #可以使用该口粮的最高等级
    max-level: 20
    
    #可以使用该口粮的宠物的id
    #不写该节点则默认全部宠物都可以使用
    can-use-pets:
    - 'example'
  
  id2:
    name: '超级口粮[回复满]'
    regen: 'maxhealth'
    #不写等级限制则全部等级都可用
    #不写宠物限制则全部宠物都能用
```
9、语言系统更新节点
```yaml
#使用宠物口粮时 当前宠物无法使用该种类口粮
food-notpet: '当前宠物无法使用该种类口粮!'

#使用口粮时 宠物当前等级未达到口粮使用所需要的最小等级
#{0} 宠物当前等级
#{1} 该口使用所需要的最小等级
food-minlevel: '当前宠物等级为 {0} 未达到该经验丹所需要的最小使用等级 {1}'

#使用口粮时 宠物当前等级超过了口粮可以使用的最大等级
#{0} 宠物当前等级
#{1} 该口粮支持的最大等级
food-maxlevel: '当前宠物等级为 {0} 超过该口粮需要的最大使用等级 {1}'

#宠物收到伤害的提示
#{0} 宠物当前血量
#{1} 宠物最大血量
pet-damage: '宠物受伤!血量 {0}/{1}'

#宠物死亡提示
pet-death: '你的宠物死亡了!'

#宠物死亡无法召唤
cant-spawn: '宠物无法召唤,因为已经死亡!请先用道具回复血量!'

#宠物帮助拾取时提示
#{0} 物品名字
#{1} 物品数量
pickup: '宠物帮你拾取了 {0} * {1}个,已放入您的背包或者脚下!'
```
10、宠物的名字/物品Lore节点中，可以用{4}代指宠物当前血量、{5}代指宠物最大血量
请一定要更新至最新版BerryLib！！！！！！！！！
11、更新宠物拾取系统，宠物能够帮忙拾取，见上pet-attribute增加的节点的注释

---

2023-2-10更新记录
1、兼容DungeonPlus，修复进副本宠物不召唤的问题
2、修复升级脚本不执行的问题
3、修复宠物口粮不支持颜色名字的问题
4、在宠物配置文件新增配置
```yaml
#宠物基本设置
#基本设置中的全部节点都不可删除!必须填写!
pet-basic-data:

  #宠物物品设置
  bind-item:
    #物品材质 全英文大写
    #注意！！！！不要让该材质的物品能叠加放！否则可能会造成bug 最好是唱片啥的，最好不要让他叠加
    type: 'PAPER'
    #如果是头颅 在这里填写skinValue
    #例如eyJ0ZXh0dXJlcyI6eyJTS0lOIjp7InVybCI6Imh0dHA6Ly90ZXh0dXJlcy5taW5lY3JhZnQubmV0L3RleHR1cmUvZDE3MTU3ZjNkYzNlMWE1OTJiNDNiNGVmN2UxNjg3OTRlYzYyNzEzOGExMDY1MzcyM2FkMzJjOGQxNjAyNiJ9fX0
    #可以在网站 https://minecraft-heads.com/ 查看
    #不需要的话请删除该节点！！！
    skinValue: ''
    #物品展示名
    name: '&b测试宠物'
    #物品lore 支持替换符 {0}当前等级   {1}最大等级 {2}当前经验 {3}下一级所需经验 {4}宠物当前血量 {5}宠物最大血量
    #lore只是用来给玩家看的 不起加属性的作用 请关闭宠物/宠物装备槽位的加属性功能
    lore:
    - '&b-----宠物物品-----'
    - '&a当前等级: {0}/{1}'
    - '&a当前经验: {2}/{3}'
    - '&a宠物血量: {4}/{5}'
    - '&a增加攻击: 10 * {0}'
    - '&b其他写法: #level * 10# 这中间会被替换为公式并计算,level代表宠物等级'
    
    #新增功能
    #以下行数的Lore不会被刷新！
    #行数从0开始计算
    #不写则默认每一行都会刷新
    #用来防止绑定的Lore被刷新掉等其他插件修改的宠物物品的Lore
    not-update:
    - 1
    - 2
```

防止刷新物品导致绑定Lore消失等问题
 5、 slot.yml加入节点  
```yaml
#新增配置 2023-2-10
#当宠物槽位包含指定Lore时 无法放入
limitLore:
  #槽位名字
  宠物_槽位:
  #包含以下Lore时无法放入槽位
  - '未绑定不能放入槽位'
```

---

2023-2-11更新
1、宠物CatServer兼容完毕，请使用官网最新版1.12.2的cat核心!
2、给MythicMobs增加了两个技能选择器如下
```yaml
berrypetowner 当技能是宠物实体释放时，目标为宠物主人
berrypetself 当技能是主人释放时，目标为自己的全部宠物
```
使用方法：
1）加入MythicExtension插件（群文件有），并开服生成文件夹
2）将BerryPetMMEx.jar下载（群文件）放入plugins\MythicMobsExtension\externals中
3）重启服务器即可加载
