## YEP.38 Battle System – Charge Turn Battle
***
### Introduction - 插件介绍
***

 The Battle System - Charge Turn Battle plugin is an extension plugin forYanfly Engine Plugins' Battle Engine Core. This extension plugin will not work without the main plugin.

 To use the CTB system, go to the Battle Engine Core plugin and change the 'Default System' setting in the parameters to 'ctb'.

 The Charge Turn Battle system functions by calculating every battlers' speed and balancing them relative to one another. When it's a battler's turn, the battler will either choose an action to perform immediately or charge it for later depending if the skill requires charging.

 This is a battle system where agility plays an important factor in the progress of battle where higher agility values give battlers more advantage and lower agility values give battlers less advantage.

 OK,其实我很乐意给这类战斗插件做翻译,CTB系统也是一个很经典的回合战斗系统.你一定玩过空轨、碧轨、零轨对吧，那你一定对这种战斗系统不陌生,类似于ATB系统,CTB系统也有一个行动槽,但是与ATB不同,他是所有角色统一的一个排位槽,角色根据自身敏捷进行排位槽积攒排位值,最先攒满的角色进行行动,行动中角色可以使用立即施放,或需咏唱一段时间的技能，在选择咏唱技能后,其他角色的行动槽将继续增长,到达顶点后开始行动.

 类似与ATB插件,本插件也将依靠Battle Engine Core核心插件,安装时务必位于核心插件下方
 同时要启用CTB战斗系统,你也需要在核心插件的Default System选项中 将键值修改为CTB即可

***
### Plugin Commands 插件命令
***

 To change your battle system to Charge Turn Battle if it isn't the default battle system, you can use the following Plugin Command:
 
 与ATB系统的设置相同,CTB模式也允许你是用插件命令在游戏内切换游戏模式

#### Plugin Command:
 插件命令:
 
	setBattleSys CTB      
   
   设置为CTB系统
   
	setBattleSys DTB      
   
   设置为DTB系统.

 Using the above Plugin Commands, you can toggle between the Default Battle System and Charge Turn Battle!
 使用事件内的插件命令,可以实现在游戏内部对战斗系统的转换功能.

***
### Notetags-注释命令
***

 The following are notetags that pertain to and affect the CTB system.
 下面的注释命令只会在你启用了CTB战斗系统时生效.

#### Actor and Enemy Notetags:
 玩家角色和敌人注释命令:
 
 	<CTB Icon: x>
 	
   设置角色或敌人的CTB排位槽的头像图标.

	<CTB Border Color: x>
   
   设置角色或敌人的CTB排位槽的边框线条颜色.

	<CTB Background Color: x>
   
   设置角色或敌人的CTB排位槽的边框背景颜色.

#### Actor only Notetags:
 仅可用于玩家角色的注释命令
 
	<Class x CTB Icon: y>
   
   This sets it so that if the actor is a specific class, the actor will get a specific icon used for the CTB Turn Order. If the actor is class x, it will receive icon y.
   
   给不同职业定义不同的头像图标,x为职业ID,y为头像ID

	<Hero CTB Icon: x>
	<Warrior CTB Icon: x>
	<Mage CTB Icon: x>
	<Priest CTB Icon: x>
	
   If you prefer to use names instead of class ID's, you can use the above notetag format. If the actor is the named class, it will receive icon x.
   If you have multiple classes with the same name, priority will be given to the class with the highest ID.
   
   如果你要使用职业名称来定义头像也是可以的,但写法略有不同,把上面class x直接替换为职业名称即可.

#### Skill and Item Notetags:
 技能和道具注释命令:
 	
	<CTB Help>
	text
	text
	</CTB Help>
	
   For those planning on using multiple battle systems, sometimes you may have your skills perform differently while using CTB. If so, using this notetag will allow skills and items to display different help text while CTB is enabled.
   
   给技能和道具添加一个专属的CTB说明信息,这个信息只有在CTB系统启用时会显示.

	<CTB Speed: x>
	
   Usable only during CTB. This sets the target's current speed to x.
   
   把目标的当前排位值设置为x,这个类似于ATB的speed值

	<CTB Speed: x%>
	
   Usable only during CTB. This sets the target's current speed to x% of the CTB turn completion target.
   把目标的当前排位值设置x%,100%就是直接行动

	<CTB Speed: +x>
	<CTB Speed: -x>
	
   Usable only during CTB. This increases or decreases the target's current speed by x.
   
   把目标的当前排位值增加或减少x +/- 起到快速行动或延迟行动的目的

	<CTB Speed: +x%>
	<CTB Speed: -x%>
	
   Usable only during CTB. This increases or decreases the target's current speed or charge by x% of the CTB turn completion target.
   
   你也可以使用+/-百分比的形式进行定义

	<CTB Order: +x>
	<CTB Order: -x>
	
   Moves target's position in the turn order by +x or -x. +x will make the target having to wait more before getting their turn while -x will make the target having to wait less. The effect is minimal and will only last for the current turn cycle.
   
   使用这个命令按照x参数改变当前目标的综合排序,+x会使目标需要等待更长的时间.这个命令的效果微小,并且只会持续到当前回合的循环结束
   
   Note: If you use this for multiple targets, each target will shift turns individually at a time.
   
   要注意：如果你的命令针对了多个目标,每个目标的回合变化将会分别计算
   翻译者解释：其实就是按照x排序啦,比如你写+1就是把目标的行动推后1位,由于只在当前回合的循环轮生效,所以+100和+1000的效果都是推到最后,但是+1000肯定能够要比+100更靠后.如果x相同,那么将会根据原来的角色顺序排序.这个命令我认为作者其实主要想用来微调某个角色的行动顺序的功能,因为靠speed参数来调整需要的计算量比较大,而且很不稳定.而这个+1 +2 -1 -2的排序功能设定起来就相对容易多了.

	<After CTB: x>
	<After CTB: x%>
	
   This will set the skill/item user's CTB speed value to x or x%. If 'x' is used, this will be the exact CTB value. If x% is used, this will be the percentage of the CTB turn completion target that it will be at.
   
   在行动结束后,将排位槽的值设置为x或x%

#### Actor, Class, Enemy, Weapon, Armor, and State Notetags:
 角色,职业,敌人,武器,护甲和状态命令:
 
	<CTB Start: +x>
	<CTB Start: +x%>
	
   Usable only during CTB. This will give the actor, class, enemy, weapon,armor, or state the property of starting battle with X CTB Speed or X% of the CTB turn completion target.
   
   在CTB模式中,定义角色开始时的排序槽值,第一次行动后从0开始排位.

	<CTB Turn: +x>
	<CTB Turn: +x%>
	
   Usable only during CTB. This will give the actor, class, enemy, weapon,armor, or state the property of starting a turn with X CTB Speed or X% of the CTB turn completion target.
   
   每回合开始时目标的排序槽值,行动后依然从x或x%处开始排位.

***

### Happy RPG Making!