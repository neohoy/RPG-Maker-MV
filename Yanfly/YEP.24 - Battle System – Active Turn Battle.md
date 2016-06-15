## YEP.24 – Battle System – Active Turn Battle
The ever so popularly requested battle system: ATB! Made similarly to match the Final Fantasy series, the ATB system starts off with your characters filling up their gauges before they can input an action. Once an action is inputted, they start to quickly charge it up before going to perform their attack.

This plugin requires the Battle Engine Core plugin.

***
###Introduction
***

The Battle System – Active Turn Battle plugin is an extension plugin for Yanfly Engine Plugins’ Battle Engine Core. This extension plugin will not work without the main plugin.

To use the ATB system, go to the Battle Engine Core plugin and change the ‘Default System’ setting in the parameters to ‘atb’.

The Active Turn Battle system functions in such where battlers will have a new gauge in battle functioning as their turn gauge. As time goes by without anything happening such as actions, menu selection, etc, the gauge fills up. Once it is full, the battler can commit to an action.

After committing to an action, the battler charges the skill before using it in battle to either attack an enemy, heal an ally, etc. Upon finishing the action, the gauge drains to empty and the battler must charge it up again.

This is a battle system where agility plays an important factor in the progress of battle where higher agility values give battlers more advantage and lower agility values give battlers less advantage.

***
### Plugin Commands
***

To change your battle system to Active Turn Battle if it isn’t the default battle system, you can use the following Plugin Command:

#### Plugin Command:

	setBattleSys ATB
Sets battle system to Active Turn Battle.

	setBattleSys DTB
Sets battle system to Default Turn Battle.

Using the above Plugin Commands, you can toggle between the Default Battle System and Active Turn Battle!

***
### Notetags
*** 

The following are notetags that pertain to and affect the ATB system.

Skill and Item Notetags:

	<ATB Help>
	text
	text
	</ATB Help>
For those planning on using multiple battle systems, sometimes you may have your skills perform differently while using ATB. If so, using this notetag will allow skills and items to display different help text while ATB is enabled.

	<ATB Speed: x>
	<ATB Charge: x>
	<ATB Gauge: x>
Usable only during ATB. This sets the target’s current speed or charge to x. If ‘speed’ or ‘charge’ is used, it will only affect those gauges while in the respective phase. If ‘gauge’ is used, it will affect either.

	<ATB Speed: x%>
	<ATB Charge: x%>
	<ATB Gauge: x%>
Usable only during ATB. This sets the target’s current speed or charge to x% of the whole gauge. If ‘speed’ or ‘charge’ is used, it will only affect those gauges while in the respective phase. If ‘gauge’ is used, it will affect either.

	<ATB Speed: +x> or <ATB Speed: -x>
	<ATB Charge: +x> or <ATB Charge: -x>
	<ATB Gauge: +x> or <ATB Gauge: -x>
Usable only during ATB. This increases or decreases the target’s current speed or charge by x. If ‘speed’ or ‘charge’ is used, it will only affect those gauges while in the respective phase. If ‘gauge’ is used, it will affect either.

	<ATB Speed: +x%> or <ATB Speed: -x%>
	<ATB Charge: +x%> or <ATB Charge: -x%>
	<ATB Gauge: +x%> or <ATB Gauge: -x%>
Usable only during ATB. This increases or decreases the target’s current speed or charge by x% of the whole gauge. If ‘speed’ or ‘charge’ is used, it will only affect those gauges while in the respective phase. If ‘gauge’ is used, it will affect either.

	<After ATB: x>
	<After ATB: x%>
This will set the skill/item user’s ATB speed value to x or x%. If ‘x’ is used, this will be the exact ATB value. If x% is used, this will be the percentage of the ATB gauge that it will be at.

	<ATB Interrupt>
	<ATB Interrupt: x%>
This will give the skill the ability to interrupt and cancel out the target’s current action while it is in the charging phase. If the ‘x%’ notetag version is used, it will have a x% chance of success.

#### Actor, Class, Enemy, Weapon, Armor, and State Notetags:
	<ATB Start: +x>
	<ATB Start: +x%>
Usable only during ATB. This will give the actor, class, enemy, weapon, armor, or state the property of starting battle with X ATB Speed or X% of the ATB gauge filled up.

	<ATB Turn: +x>
	<ATB Turn: +x%>
Usable only during ATB. This will give the actor, class, enemy, weapon, armor, or state the property of starting a turn with X ATB Speed or X% of the ATB gauge filled up.

***
### Lunatic Mode – Conditional ATB Speed and Conditional ATB Charge
***

For those who have a bit of JavaScript experience and would like to have more unique ways of performing ATB speed and charge changes, you can use the following notetags:

#### Skill and Item Notetags:
	<Target ATB Eval>
	speed = x;
	charge = x;
	</Target ATB Eval>
You can omit speed and/or charge. Whatever you set ‘speed’ to will change the ATB speed of the target. If the target is charging, ‘charge’ will cause the target’s charge to change to that value. To make things more simple, ‘max’ will be the full gauge value.

Here is an example:

	<Target ATB Eval>
	speed = target.hp / target.mhp * max;
	charge = target.hp / target.mhp * max;
	</Target ATB Eval>
The above code will set the user’s current ATB gauge to position equal to the target’s HP ratio. If the target has 25% HP, the ATB gauge will go to 25% full for the target.

---

	<After ATB Eval>
	speed = x;
	</After ATB Eval>
This is the ATB set after the user has used the skill/item and the custom ATB amount you want the user to be at after. ‘max’ be the value of the full gauge value. Whatever you set ‘speed’, the user’s ATB speed value will change to that much:

Here is an example:

	<After ATB Eval>
	speed = user.mp / user.mmp * max;
	</After ATB Eval>
The above code will set the user’s ATB gauge after using the skill/item to equal the user’s MP ratio. If the user has 25% MP, the ATB gauge will go to 25% full for the user.

---

	<ATB Interrupt Eval>
	interrupt = true;
	</ATB Interrupt Eval>
This will allow you to set custom conditions for interrupting a target. Keep in mind that even though it is a custom condition, it still requires the target to be in the charging phase for the interrupt to work. By setting ‘interrupt = true’, the target will be interrupted.

Here is an example:

	<ATB Interrupt Eval>
	if (user.hp > target.hp) {
	interrupt = true;
	}
	</ATB Interrupt Eval>
The above code will state that if the user has more HP than the target, the target will be interrupted.

***
### Yanfly Engine Plugins – Battle Engine Extension – Action Sequence Commands
***

You can make use of these extra ATB related action sequences.

---

	ATB CHARGE: target, X
	ATB CHARGE: target, X%
	ATB CHARGE: targets, +X
	ATB CHARGE: targets, +X%

Usable only for ATB. Sets the target’s ATB charge to X or X%. This only applies when the target is in the ATB charge phase. This will not affect the user to prevent mechanical issues.

Usage Example: atb charge: targets, +5000
atb charge: target, -50%

---

	ATB GAUGE: target, X
	ATB GAUGE: target, X%
	ATB GAUGE: targets, +X
	ATB GAUGE: targets, +X%

Usable only for ATB. Sets the target’s ATB speed or charge (whichever the user is currently filling up) to X or X%. This only. This will not affect the user to prevent mechanical issues.

Usage Example: atb gauge: targets, +5000
atb gauge: target, -50%

---

	ATB INTERRUPT: target

Usable only for ATB. If the target is in the charging phase, interrupt it.

Usage Example: atb interrupt: targets

---

	ATB SPEED: target, X
	ATB SPEED: target, X%
	ATB SPEED: targets, +X
	ATB SPEED: targets, +X%

Usable only for ATB. Sets the target’s ATB speed to X or X%. This only applies when the target is filling up its ATB gauge. This will not affect the user to prevent mechanical issues.

Usage Example: atb speed: targets, +5000
atb speed: target, -50%

---

***

### Happy RPG Making!

		
>Introduction-关于本插件的介绍  
>翻译 by 抖M俱乐部的 SmithJiong/bennett01/SOAP   
>转载请感谢我！ 没错上面三个都是我！
  
---

  The Battle System - Active Turn Battle是一个基于Yanfly大神Battle Engine Core插件的拓展插件，
  所以它无法脱离核心战斗插件独立工作，安装时务必将该插件放置于战斗核心插件-Battle Engine Core下方，
  要启用ATB战斗系统，请在战斗核心插件的配置中，将Default System 选项由dtb修改为atb即可。  
 
  ATB战斗系统是一个出色的动态战斗系统，它给角色定义了一个行动槽，当行动槽填充时，角色不能进行任何操作，
  只有行动槽充满时，才可以进行相关操作如攻击、技能等等，行动后清空行动槽，当行动槽再次充满后，角色才可进行下一次行动。  
  角色选择技能以后，会进入第二阶段行动槽填充，通常被成为咏唱时间条的填充，第二阶段行动槽填满后，角色才会释放技能。  
  这种经典的战斗系统被很频繁用到了如最终幻想系列等很多游戏当中，这也使得传统RPG原本枯燥的回合战斗变得更加紧张、刺激和有趣味，
  使用本系统，将使回合战斗中的更多战术和策略技能的设计研发成为可能。  
  
  ATB战斗系统使各角色的敏捷属性不再是花瓶，敏捷将直接决定角色的出手顺序和出手速度，
  通常来说敏捷高的角色比敏捷低的角色更具备优势，前提是你不要弄个负敏神兽出来...
 

***
### 插件命令
***

  你可以使用下面的命令在游戏内事件里调用插件命令，来更改当前游戏的战斗系统：
 
#### 插件命令：
    setBattleSys ATB      将战斗模式改为 ATB 动态回合战斗系统.
    setBattleSys DTB      将战斗模式改为 DTB 默认回合战斗系统.
	使用这个命令可以实现游戏对战斗模式的实时切换。

***
### 注释命令
***

  以下为影响的ATB系统的相关注释命令
 
#### 技能与道具注释
 
    <ATB Help>
    text
    text
    </ATB Help>
    这个命令可以给技能或道具添加专有的ATB说明信息，即如果启用了ATB战斗系统，
    则在技能/道具说明中显示<ATB Help>中的text文字说明，如果使用DTB系统，则显示默认说明。
 
    <ATB Speed: x>
    <ATB Charge: x>
    <ATB Gauge: x>
    仅在ATB模式启用时可用。可以将目标单位的ATB行动值-speed、
    咏唱值-Charge、综合值-Gauge的设置为一个固定数值。简单解释：
    speed参数-决定了行动阶段行动槽的值
    Charge参数-咏唱阶段的行动槽的值
    Gauge参数-这个参数会同时影响以上两个阶段的行动槽值
    例子：道具注释中写上<ATB Speed: 1000> 即表示使用该道具后，目标的行动槽值将被设置为1000
    你要注意的是，如果你的行动槽值已经积攒到了10000，使用该道具后，将被置于1000，相当于减速，如果为0则反之。
 
    <ATB Speed: x%>
    <ATB Charge: x%>
    <ATB Gauge: x%>
    参照上面的命令，你可以将具体的X数值更换为百分比，这样ATB系统将根据行动槽最大值
    来计算你要实现的具体数值大小
    例子：道具注释中写明<ATB Charge: 50%> 表示该道具使用后咏唱槽数值将被设置为50%，如果目标未咏唱，则不生效。
    如果目标咏唱超过50%，则将被强制重置为50%，相当于减速，如果为0反之。
 
    <ATB Speed: +x>   or   <ATB Speed: -x>
    <ATB Charge: +x>  or   <ATB Charge: -x>
    <ATB Gauge: +x>   or   <ATB Gauge: -x>
    同上，你可以将x参数上加入+号或者-号来表示在当前行动槽基础上增加或者减少，这个命令通常被用于加速/减速道具或技能的设计。
    例子：<ATB Gauge: +50%>  
 
    <ATB Speed: +x%>   or   <ATB Speed: -x%>
    <ATB Charge: +x%>  or   <ATB Charge: -x%>
    <ATB Gauge: +x%>   or   <ATB Gauge: -x%>
    同上，你同样可以把增加减少数值修改为百分比。
 
    <After ATB: x>
    <After ATB: x%>
    顾名思义，你可以在道具和技能注释中加入这个命令，标识使用该道具或技能后，对使用者行动槽的影响。
    因为使用技能或道具后，行动槽必定会被清空，所以+/-就没有意义了，你要把X替换为数值或百分比。
    例子：我在电光火石这个技能的注释中加入了<After ATB: 50%>这个命令，表示我使用电光火石技能后，
    使用者的回合结束后，行动槽将从50%处开始增加，相当于下回合行动更快速了，是不是很吊？
 
    <ATB Interrupt>
    <ATB Interrupt: x%>
    这个命令比较强悍，就是打断！没错，Iterrupt命令会在对进入咏唱条的角色使用后生效，打断对方目标咏唱，
    清空目标行动槽。如果你使用了百分比参数，则表示有多少百分比的几率成功。
    例子：我在小石头这个道具的注释命令中添加了<ATB Interrupt: 50%>这个命令，表示当我使用这个道具后，
    目标如果正在咏唱，则有50%概率被打断，技能释放失败。如果目标没有在咏唱，则道具无效。
 
    <Cannot ATB Interrupt>
    当然你可以在技能中加入<Cannot ATB Interrupt>这个注释，表示该技能无法被打断，
    如果有这个命令，任何带有打断命令的技能和道具都不会对这个技能生效了,请叫我BOSS
 
#### 下面这些命令可以用在角色、职业、敌人、武器、护甲和状态注释命令中，不要用错地方哦:
 
    <ATB Start: +x>
    <ATB Start: +x%>
    上面的命令可以让你在回合开始时，获得行动槽的加成，x为数值或者百分比。第一回合结束后，行动槽将从0开始计算。
    例子：哈罗德的角色注释中我加入了<ATB Start: +20%>命令，表示哈罗德每次战斗开始时行动槽都会从20%开始计算，而不是0
    在第一回合之后，哈罗德的行动槽恢复正常，与其他角色一样从0开始。
 
    <ATB Turn: +x>
    <ATB Turn: +x%>
    这个命令表示每个回合的行动槽获得行动力加成，x为数值或者百分比。包括第一回合在内的每一个回合，行动槽都会从X或x%开始计算。
    例子：我在时魔法师的职业注释中加入了<ATB Turn: +50%>这个命令，然后我把玛莎转职成了时魔法师，但是悲剧的小明还是黑魔法师
    所以小明的行动槽每回合是从头开始计算的，而玛莎美女每回合的行动力都是从50%处开始计算，所以，玛莎比小明更快，此题得证。
 
***
### Lunatic Mode - Conditional ATB Speed and Conditional ATB Charge
  狂人模式已开启？Lunatic这个单词我并不熟..然而我也不是二次元党，
  据说二次元可以把这个词儿翻译成萝莉..
***
 
  等等，上面那些基本命令已经满足不了你的编程小心脏了吗？我们为您提供了可以在注释区域混合JavaScript脚本拓展
  命令的专用模式已经开启，Lunatic Mode 可以让你在注释命令区间内按你们的想法设置条件和触发器，前提是，你要懂
  这方面的技术。喂喂，懂脚本什么的（说我吗？）应该都懂点点E文吧，不懂的我翻了这段有啥意义吗？好纠结...掀桌
 
    技能和道具命令
    <Target ATB Eval>
    speed = x;
    charge = x;
    </Target ATB Eval>
    不同于直接的<ATB Speed/Charge/Gauge>命令,这段命令的格式如上，你可以在注释区的Lunatic Mode中
    使用更复杂的语句和公式定义speed charge参数，也支持if else while for等javascript脚本命令。
 
    给一个例子：
 
    <Target ATB Eval>
    speed = target.hp / target.mhp  max;
    charge = target.hp / target.mhp  max;
    </Target ATB Eval>
    上面这段代码实现了speed和charge按照目标单位的hp和最大hp的百分比进行修改，即目标血越少行动条填充的越多。
    延伸一点，你也可以使用触发器，使用if target.hp < target.mhp  30% 这种条件来决定这个技能什么时候可以被触发。
 
    --- --- --- --- ---
 
    <After ATB Eval>
    speed = x;
    </After ATB Eval>
    这个命令类似于<Afer ATB> 可以让你设计动作完毕后，该动作对角色行动槽的影响，当然你也可以设计的很复杂。
 
    例子君出现了：
 
    <After ATB Eval>
    speed = user.mp / user.mmp  ;
    </After ATB Eval>
    上面的代码实现了按照人物MP最大百分比来加成施法后行动条的回复量的功能。
 
    --- --- --- --- ---
 
    <ATB Interrupt Eval>
    interrupt = true;
    </ATB Interrupt Eval>
    打断，没什么好说的，加入各种触发器和公式命令都是可以的。
 
    例子君出现了：
 
    <ATB Interrupt Eval>
    if (user.hp > target.hp) {
       interrupt = true;
    }
    </ATB Interrupt Eval>
    上面的命令实现了当使用者的当前hp大于目标的hp时，打断才能成功。
    给一个延伸的例子，通常我们想要给打断技能一个固定几率，然后增加一个附加值
    比如，默认50%的概率
 
***
### Yanfly Engine Plugins - Battle Engine Extension - Action Sequence Commands
***

  下面部分的命令将会与Battle Engine带来的基础Action行为密切相关，在学习命令时
  建议先去Battle Engine插件中掌握如何使用Action Sequence的相关命令和内容
***
 
  You can make use of these extra ATB related action sequences.
  
  本插件提供了更多的关于atb系统的action sequences命令，快把他们加入到你的
  技能和战斗中来吧。
 
 
	ATB CHARGE: target, X
	ATB CHARGE: target, X%
	ATB CHARGE: targets, +X
	ATB CHARGE: targets, +X%
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  上面的命令参照charge咏唱条的设定，不过你可以把targets更换为其他值了，
  具体请参照action sequence的帮助文件
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  Usage Example: 
  
	atb charge: targets, +5000
	atb charge: target, -50%
 ---
 
 ---
	ATB GAUGE: target, X
	ATB GAUGE: target, X%
	ATB GAUGE: targets, +X
	ATB GAUGE: targets, +X%
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  参照Gauge设置，针对speed和charge两个参数同时生效。
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  Usage Example: 
  
	atb gauge: targets, +5000
	atb gauge: target, -50%
 ---
 
 ---
	ATB INTERRUPT: target
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  打断命令，没什么好说的，用sequence系统可以做成群体打断，全体打断，打断自己人，好开心
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  Usage Example: 
  
	atb interrupt: targets
 ---
 
 ---
	ATB SPEED: target, X
	ATB SPEED: target, X%
	ATB SPEED: targets, +X
	ATB SPEED: targets, +X%
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  参照speed参数设置，你可以实现更多目标
 - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
  Usage Example: 
  
	atb speed: targets, +5000
	atb speed: target, -50%
 ---
 ***

### Happy RPG Making!