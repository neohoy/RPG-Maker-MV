##YEP.54 – Row Formation
***
###Introduction
***
This plugin places party members into row formations to give them distinct advantages based on row location in the form of states for maximum control. Skills and items are capable of moving targets to different row locations.

这个插件把队员编队并且让他们根据状态有不同的位置。技能和物品可以用来移动目标

If you are using YEP_BattleEngineCore.js, place this plugin under the YEP_BattleEngineCore.js plugin in the Plugin Manager list to receive extra features such as being able to change Rows mid-battle.

如果你使用了YEP_BattleEngineCore，把这个插件放在YEP_BattleEngineCore下面，这样你就可以在战斗中改变队列
***
###What are Rows?
***

Rows are positions your party members are placed in. Depending on how you set up the rows for your project (and how many), rows can provide different advantages to the party members for just simply being in that row.

队列就是你队伍成员所在位置。你可以设置你队伍的排列，然后就可以调整队伍成员的位置

These advantages are granted through the states that are given to the party members from the plugin parameter settings. How you set up these advantages is entirely up to you.

这些位置将可以通过插件参数提供给角色相应状态来获得。怎么设置将取决于你

—

An example of some setups:

关于设置的例子

Front Row:
Members in the front row will receive full damage from the Melee element.

前排将会承受混战的全部伤害

Middle Row:
Members in the middle row will receive slightly less damage from the Melee element, but the Attack command is sealed unless they have a ranged weapon.

中间排将会受到少量伤害，但是他们必须有范围武器才可以攻击

Back Row:
Members in the back row will receive a lot less damage fom the Melee element and also cannot use the Attack command unless equipped with a ranged weapon.

后排会受到极少伤害，但是他们必须有范围武器才可以攻击

—

How you choose to set up your rows is dependent on how you can set up your states that affect those rows. These states cannot be removed by skills and are considered a passive effective.

你如果设置队取决于你设置的状态。这些状态不可以被技能移除并且是主动效果

***
###Notetags
***

You can use these notetags to modify the various aspects of row formations.

你可以使用下面的标签来调整队列

####Actor and Enemy Notetags:

	<Default Row: x>
This is the default row assigned to the battler by default. This will override the default parameter settings.

默认队列为x

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Row Lock>
This causes the affected battler to be row locked and unable to switch rows. For enemies, this will override the default parameters.

锁定队列

	<Not Row Lock>
This causes the affected battler to be not be row locked and able to switch rows. This is primarily for enemies since all non-enemies are not row locked by default. This will override the default parameters.

解锁队列

####Skill and Item Notetags:

	<Row Only: x>
	<Row Only: x, x, x>
	<Row Only: x to y>
This makes it so that this skill/item can only be used by the battler if the battler is in row x. If multiple rows are used, the battler can be in any of those rows. If you use the x to y notetag, this will account for all the rows from x to y.

只有位于队列x才能使用技能或者物品

	<Change Target Row: x>
Changes target’s current row to x. This cannot go under 1 nor can it go past the designated maximum row set in the parameters.

改变目标队列为x

	<Push Back Target Row: x>
This will push the target back x rows. This cannot exceed the maximum row set in the parameters.

目标队列后退x排

	<Pull Forward Target Row: x>
This will pull the target forward x rows. This cannot exceed the maximum rows set in the parameters.

目标队列前进x排

	<Change User Row: x>
Changes user’s current row to x. This cannot go under 1 nor can it go past the designated maximum row set in the parameters.

改变使用者队列为x

	<Push Back User Row: x>
This will push the user back x rows. This cannot exceed the maximum row set in the parameters.

使用者队列后退x排

	<Pull Forward User Row: x>
This will pull the user forward x rows. This cannot exceed the maximum rows set in the parameters.

目标队列前进x排

***
###Plugin Commands
***

The following are some plugin commands you can use to adjust rows mid-game.

下面的插件命令可以用来调整队列

####Plugin Command:

	ShowMenuRow
	HideMenuRow
This will either show or hide the Row command from the main menu.

显示或隐藏主菜单队列命令菜单

	EnableMenuRow
	DisableMenuRow
This will either enable or disable the Row command from the main menu.

开启或关闭主菜单队列命令菜单

	ShowBattleRow
	HideBattleRow
This will either show or hide the Row command from the battle party menu. This requires the YEP_BattleEngineCore plugin to take effect.

显示或隐藏战斗菜单队列命令菜单

	EnableBattleRow
	DisableBattleRow
This will either enable or disable the Row command from the battle party menu. This requires the YEP_BattleEngineCore plugin to take effect.

开启或关闭战斗菜单队列命令菜单

	SetActorRow actorId x
This will set the actor represented by actorId to move to row x. If you want to move actor 3 to the 2nd row, the plugin command would look like: SetActorRow 3 2

设置角色队列为x排

	SetPartyRow slotId x
This will set the party member in slotId to move to row x. If you want to move the 3rd party member to the 2nd row, the plugin command would look like: SetPartyRow 3 2

设置队伍成员队列为x排

	SetEnemyRow slotId x
This will set the enemy member in slotId to move to row x. If you want to move the 3rd enemy member to the 2nd row, the plugin command would look like: SetEnemyRow 3 2

设置敌方成员队列为x排

Note: If you use this plugin command during turn 0, the enemies will not move and automatically assume the position they are in will be the row they’ll be in. On the other hand, using this plugin on anything after turn 0 will move the enemy visually to a different position on the screen.

注意：如果你在回合0时使用插件命令，敌方不会移动，并且自动认为现在的位置就是将要去的位置。另一方面，在回合0之后使用将会移动敌人到不同的位置

***
###Happy RPG Making!

