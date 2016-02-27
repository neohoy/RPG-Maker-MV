##YEP.64 – Enemy Levels
***
###Introduction
***

This plugin allows enemies to function off of a leveling system. An enemy’s level will be increased relative to the player under specific rulings and will increase its stats based on its level.

这个插件允许敌方可以等级系统。通过特殊的规则，敌方等级可以提升，并且基于等级提升状态

***
###Default Level Types
***

When an enemy is made in battle, it will create its initial level off of a set of rules. These are the various rules you can change the ‘Default Type’ plugin parameter to reflect.

当敌方在战斗中时，将会创造初始等级。这里有很多规则你可以用来改变默认类型

Type:

– Type 0 – Lowest level of all actors that have joined the player party.  
– Type 1 – Lowest level of all actors that are in the battling party.  
– Type 2 – Average level of all actors that have joined the player party.  
– Type 3 – Average level of all actors that are in the battling party.  
– Type 4 – Highest level of all actors that have joined the player party.  
– Type 5 – Highest level of all actors that are in the battling party.  

类型0-角色队伍里最低等级  
类型1-战斗队伍里最低等级  
类型2-角色队伍里平均等级  
类型3-战斗队伍里平均等级  
类型4-角色队伍里最高等级  
类型5-战斗队伍里最高等级  

After the level type has been determined for the enemy, random level fluctuations are then added.

在等级类型决定之后，会添加等级波动

***
###Notetags
***

You can use these notetags to adjust how enemy levels are handled individually per enemy.

你可以使用下面的标签来调整敌方等级

####Enemy Notetags:

	<Show Level>
	<Hide Level>
This will cause the enemy to show or hide its level upon target selection.

显示或者隐藏敌方等级

	<Minimum Level: x>
	<Maximum Level: x>
This sets the enemy’s minimum and maximum levels respectively to x. This will cause the enemy, upon the start of battle, to adjust levels within this particular range. Any skills that alter enemy levels are able to bypass these limits unless if it were to bypass the maximum cap.

设置敌方最小和最大等级x。这将造成敌人战斗开始等级将会在这个范围波动。任何改变敌方等级的技能都可以不受这个限制除非超过最大上限

	<Static Level: x>
This sets the enemy’s starting level to exactly x. This will cause the enemy, upon the start of battle, to adjust levels within this particular range. Any skills that alter enemy levels are able to bypass these limits unless if it were to bypass the maximum cap.

设置敌方初始等级x.这将造成敌人战斗开始等级将会在这个范围波动。任何改变敌方等级的技能都可以不受这个限制除非超过最大上限

<Starting Level Type: x>
This sets the enemy’s starting level type to x from 0 to 5. Refer to the ‘Default Level Types’ party of the Help File.

设置敌方初始等级类型x。

	<Positive Level Fluctuation: x>
	<Negative Level Fluctuation: x>
This sets the positive/negative level fluctuation for the enemy. Any level fluctuation is calculated at the start of battle, but after the starting level type has been determined.

设置等级的正波动和负波动。等级波动在战斗开始并且等级类型选择之后计算好

	<Level Fluctuation: x>
This sets both the positive and negative level fluctuation for the enemy to x. Any level fluctuation is calculated at the start of battle, but after the starting level type has been determined.

设置等级波动x。等级波动在战斗开始并且等级类型选择之后计算好


	<stat Rate: +x% per level>
	<stat Rate: -x% per level>
	<stat Rate: +x.y per level>
	<stat Rate: -x.y per level>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘exp’, or ‘gold’. This will set this enemy to have an increase or decrease of x% rate per level. If you use the x.y formula, it will have a rate increase of +x.y or -x.y per level.

可以按比例改变多个状态。这将改变每次提升等级，改变状态。

	<stat Flat: +x per level>
	<stat Flat: -x per level>
	<stat Flat: +x.y per level>
	<stat Flat: -x.y per level>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘exp’, or ‘gold’. This will set this enemy to have an increase or decrease of flat x value per level. If you use the x.y formula, it will have a flat increase of +x.y or -x.y per level.

可以直接改变多个状态。这将改变每次提升等级，改变状态。

<Resist Level Change>
This will cause the enemy to be immune to any form of level changing through skills and items. However, the enemy is not immune to any level changing through script calls.

这可以让地方不受任何改变等级的技能或者物品影响。但是敌方不能免疫脚本的修改

	<Skill x Require Level: y>
	<Skill name Require Level: y>
If this enemy is to use skill x (or named skill), it must be at least level y to be able to use it. If the enemy is under level y, the skill will be sealed and cannot be used.

如果敌方想要使用技能x，他必须最低等级为y。如果低于等级y，技能则被封存不能使用

####Skill and Item Notetags:

	<Reset Enemy Level>
This will reset the target enemy’s level back to what it was at the start of battle.

重置敌方等级

	<Change Enemy Level: +x>
	<Change Enemy Level: -x>
If this action is used against an enemy, it will change the enemy’s level by +x or -x. If an action contains both a reset and level change, the reset will occur first before the level change.

如果行动目标是敌方，则会改变其等级。如果行动包含重置和等级改变，重置效果将会优先发动

***
###Plugin Commands
***

If you wish to change enemy levels through plugin commands, you can use the following plugin commands to alter them. These plugin commands are only used inside battle.

如果你想要通过插件命令改变敌方等级。你可以用下面的命令改变。只可以在战斗中使用

####Plugin Command:

	EnemyLevelChange 2 to 50
– This will reset the enemy in position 2’s level to 50.

重置位置2的敌方等级为50

	EnemyLevelChangeAll 50
– This will change the levels of all enemies to 50.

重置所有敌方等级为50

	EnemyGainLevel 3 by 20
– This will cause the enemy in positon 3 to gain 20 levels.

增加位置3的敌方等级20

	EnemyGainLevelAll 20
– This will cause all enemies to gain 20 levels.

增加所有敌方等级20

	EnemyLoseLevel 4 by 10
– This will cause the enemy in positon 4 to lose 10 levels.

减少位置4的敌方等级10

	EnemyLoseLevelAll 10
– This will cause all enemies to lose 10 levels.

减少所有敌方等级10

	EnemyLevelReset 5
– This will reset the enemy in position 5’s level to the level it had at the start of battle.

重置位置5的敌方等级

	EnemyLevelResetAll
– This will reset all enemy levels to their original levels.

重置所有敌方等级

***
###Happy RPG Making!

