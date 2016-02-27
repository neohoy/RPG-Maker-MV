##YEP.27 – Job Points
This plugin by itself will not change any major game functions, but instead, it works in combination with other plugins that make use of this plugin’s functions should you decide to incorporate Job Points into your game.

这个插件不会改变游戏的主要功能，但是相反，你可以结合其他插件来结合职业点放入游戏

>Add Ons

>1. Fox’s JP Levels – This plugin adds levels to the Yanfly’s JobPoint System, like Final Fantasy Tactics had. It allows for restrictions on what skills your allowed to buy with the SkillLearnSystem based on the current classes’ Job Level. It allows for restrictions on what class your allowed to equip with the ClassChangeCore based on the current classes’ Job Level. The Job automatically gains levels just by gaining JobPoints.  
这个插件为为职业点系统添加了等级，就像最终幻想那种。允许为利用技能学习系统购买的技能添加限制，为职业改变系统改变的职业添加限制。职业将通过获得职业点自动升级  
2. MuteDay’s Job Point Extension – This plugin adds extended functionality to Job Points, by allowing trickle mechanics and how much subclasses gain while gaining JP for the primary class.  
这个插件拓展了职业点功能，允许其缓慢增加并且可以设置主职业获得点数同时副职业的获得数  
3. MuteDay’s Job Mastery – if you have learned all learnable skills for a job it gets marked as mastered and if you have Fox’s addon it will visibly show that on the menu.  
如果你学习了某个职业所有的技能，你就成为大师，如果你使用了Fox插件，你可以让它显示在菜单上

***
###Introduction
***

This plugin by itself will not change any major game functions, but instead, it works in combination with other plugins that make use of this plugin’s functions should you decide to incorporate Job Points into your game.

这个插件不会改变游戏的主要功能，但是相反，你可以结合其他插件来结合职业点放入游戏

When Job Points are earned, they are given to the actor’s current class. If the actor were to switch classes, then the Job Points will be changed to that class’s Job Points until reverted back.

当获得职业点时，他们赋予给玩家的职业。如果玩家切换职业，职业点将会变成这个职业的，除非他们被还原。

***
###Victory Aftermath Compatibility
***

If you have the YEP_VictoryAftermath plugin installed and wish to make use of the JP windows, position this plugin lower than YEP_VictoryAftermath in the Plugin Manager.

如果你有YEP_VictoryAftermath这个插件并且希望使用JP窗口，你可以把这个放在YEP_VictoryAftermath下面

After that, if you wish to define the timing of the JP window to appear at a certain point instead of the plugin doing it automatically, insert “JP” in the “Victory Order” parameter within Victory Aftermath where you want the JP window to appear.

在这之后，如果你希望决定JP窗口出现的时间，可以插入“JP”在“Victory Order” 参数里

***
###Notetags
***

Here are some notetags related to Job Points.

这里有一些标签

####Actor Notetags
	<Starting JP: x>
Sets the actor’s starting JP value to be x for the actor’s initial class.

设置职业初始职业点

	<Class x Starting JP: y>
Sets the actor’s starting JP value for class x to be y.

设置职业x的初始职业点y

	<JP Rate: x%>
This changes the rate of JP gained by x%. By default, all objects have a default rate of 100%. Increasing this to 200% will increase JP gained by twice as much while 50% will halve the amount of JP gained.

设置职业点增加率。默认是100%。如果设置200%则会获得2倍职业点，50%则获得一半。

####Skill and Item Notetags
	<JP Gain: x>
This makes it so that the actor using this skill or item will gain x amount of JP instead of the default amount of JP found in the parameters.

使用技能或者物品可以获得x个职业点

	<Target JP Gain: x>
This makes it so that the target actor affected by this skill or item will gain x amount of JP.

目标角色可以获得x个职业点

####Class, Weapon, Armor, and State Notetag
	<JP Rate: x%>
This changes the rate of JP gained by x%. By default, all objects have a default rate of 100%. Increasing this to 200% will increase JP gained by twice as much while 50% will halve the amount of JP gained.

设置职业点增加率。默认是100%。如果设置200%则会获得2倍职业点，50%则获得一半。

####Enemy Notetag
	<JP: x>
When the enemy is defeated, the party members present will gain x JP each.

敌方被击败时，每个队伍成员获得x职业点

***
###Plugin Commands
***

For those wondering how to manually give, remove, or set JP for an actor, you can use the following Plugin Commands.

如果你手动赋予，移除或者设置职业点给玩家，你可以用下面的插件命令

####Plugin Commands:

	gainJp actorId jp
	gainJp actorId jp classId
Replace ‘actorId’ with the ID of the actor you wish to change the JP of. Replace ‘jp’ with the amount of JP you wish to alter. If you are using ‘classId’, replace it with the ID of the actor’s class you wish to alter. This command will let the actor gain JP.

指定ID的角色甚至指定职业获得职业点

	loseJp actorId jp
	loseJp actorId jp classId
Replace ‘actorId’ with the ID of the actor you wish to change the JP of. Replace ‘jp’ with the amount of JP you wish to alter. If you are using ‘classId’, replace it with the ID of the actor’s class you wish to alter. This command will cause the actor to lose JP.

指定ID的角色甚至指定职业失去职业点

	setJp actorId jp
	setJp actorId jp classId
Replace ‘actorId’ with the ID of the actor you wish to change the JP of. Replace ‘jp’ with the amount of JP you wish to alter. If you are using ‘classId’, replace it with the ID of the actor’s class you wish to alter. This command will set the actor’s JP to a particular value.

指定ID的角色甚至指定职业的职业点

***
###Happy RPG Making!

