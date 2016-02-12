## YEP.59 – Aftermath Level Up

This plugin is an extension plugin for the Victory Aftermath plugin. This adds a level up section to the Victory Aftermath sequence to show the individual parameter changes the actor has acquired in addition to skills that the actor may have learned. This segment will be omitted if there are no actors to level up or if the game has the segment disabled. When there are multiple actors leveling up, the Victory Aftermath will cycle through each of the actors.

这是胜利窗口插件的拓展插件。这个可以增加胜利后升级的选项，来让玩家可以获得额外的技能。如果没有玩家升级或者关闭设置，这个效果会被忽略。当多名玩家升级，插件会循环执行每个角色。

***
### Introduction
***

This plugin requires YEP_VictoryAftermath. Make sure this plugin is located under YEP_VictoryAftermath in the plugin list.

这个插件需要“胜利窗口”插件。请确保他放在YEP_VictoryAftermath的下面。

This adds a level up section to the Victory Aftermath sequence to show the individual parameter changes the actor has acquired in addition to skills that the actor may have learned. This segment will be omitted if there are no actors to level up or if the game has the segment disabled. When there are multiple actors leveling up, the Victory Aftermath will cycle through each of the actors.

这是胜利窗口插件的拓展插件。这个可以增加胜利后升级的选项，来让玩家可以获得额外的技能。如果没有玩家升级或者关闭设置，这个效果会被忽略。当多名玩家升级，插件会循环执行每个角色。

***
###Instructions
***

While this plugin is plug and play (and doesn’t require much change), if you wish to change the order of when the level up process occurs, insert ‘level’ in the ‘Victory Order’ parameter within the Victory Aftermath plugin’s parameters at the location to appear.

当这个插件插入并且执行时，你可以改变升级后事件顺序，插入“等级”在
“胜利顺序”参数里。

***
###Plugin Commands
***

You can use these plugin commands to adjust whether or not the Level Up portion of the Victory Aftermath will occur.

你可以用下面的命令调整胜利窗口是否有升级效果

#### Plugin Command:

	ShowVictoryLevelUp
	
This will cause the level up segment of the Victory Aftermath to appear if there is an actor that leveled up in the current battle.

开启胜利后升级效果

	HideVictoryLevelUp
	
This will cause the level up segment of the Victory Aftermath to not appear at all regardless of any actors leveling up in that battle.

关闭胜利后升级效果

***
### Happy RPG Making!