##YEP.55 – Enhanced TP
***
###Introduction
***
The TP system in RPG Maker MV is rather limiting. A lot of the TP system is hardcoded in giving RPG Maker MV users very little control over how much TP gain a battler can receive from particular actions and situations. This plugin gives you the ability to adjust how much TP battlers will acquire various actions, different TP modes, and letting players selecting and pick what TP mode they want for each actor.

TP系统在MV软件里比较受限制，很难控制一场战斗中TP的获得数。这个插件可以让我们调整不同行动获得TP数，更改TP模式等

***
###Instructions – TP Mode Parameters
***
TP Modes are given to your actors for them to decide how they want to gain TP over the course of battle. You can decide the rulings for each TP Mode.

TP模式决定着战斗中获得的TP数。你可以更改每个模式的规则

Here is an overview of what each TP Mode Parameter does:

下面是关于各个模式参数的介绍

Name
– This is the name of the TP Mode. This is what appears in the TP Mode selection menu in the Skill Menu (if you have it enabled).

显示在TP模式选择菜单的名字

Icon
– This is the icon used for the TP Mode in the TP Mode selection menu in the Skill Menu (if you have it enabled).

显示在TP模式选择菜单的图标

Help Line 1
Help Line 2
– This is the help description used for the TP Mode in the TP Mode selection menu in the Skill Menu (if you have it enabled).

显示在TP模式选择菜单的帮助文本

Preserve
– If set to true, then the user carries any earned TP from on battle to the next battle. If set to false, the at the start and each of each battle the user’s TP value is cleared.

每次战斗之后可以储存TP数，如果关闭则每次战斗开始都会清零

Initial TP
– This is the formula to determine how much TP is gained at the start of battle. Previously, this was reserved for non-preserved TP values. Now, it can be used regardless.

初始TP数

Regen TP
– This is how much TP is regenerated during the regeneration phase for the user. Typically, the regeneration phase occurs at the end of each turn.

每回合生成的TP数

Take HP DMG
– This is how much TP is generated from the user taking HP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

受到伤害生成的TP数

Deal HP DMG
– This is how much TP is generated from the user dealing HP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

造成伤害生成的TP数

Heal HP DMG
– This is how much TP is generated from the user healing HP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

治疗生成的TP数

Ally HP DMG
– This is how much TP is generated from an ally taking HP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

队员受到伤害生成的TP数

Take MP DMG
– This is how much TP is generated from the user taking MP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

受到MP损失生成的TP数

Deal MP DMG
– This is how much TP is generated from the user dealing MP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

造成MP损失生成的TP数

Heal MP DMG
– This is how much TP is generated from the user healing MP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

恢复MP损失生成的TP数

Ally MP DMG
– This is how much TP is generated from an ally taking MP damage. The amount of damage taken can be retrieved from the ‘value’ variable.

队友受到MP损失生成的TP数

Deal State
– This is how much TP is generated from the user issuing a state on a foe. If the user and target are on the same team, ignore this.

施与状态生成的TP数

Gain State
– This is how much TP is generated from the user gaining a state from a foe. If the user and origin are on the same team, ignore this.

获得状态生成的TP数

Kill Ally
– This is how much TP is generated if an allied member dies. It does not matter who the killer is.

队友死亡生成的TP数

Kill Enemy
– This is how much TP is generated if an enemy member dies. It does not matter who the killer is.

敌方死亡生成的TP数

Win Battle
– This is how much TP is generated from the player winning a battle.

战斗胜利生成的TP数

Flee Battle
– This is how much TP is generated from the player escaping a battle.

战斗逃跑生成的TP数

Lose Battle
– This is how much TP is generated from the player losing a battle.

战斗失败生成的TP数

Crisis HP
– This is how much TP is generated during the Regen TP timing if the user is in a critical HP state.

HP较少时TP获得数

Crisis MP
– This is how much TP is generated during the Regen TP timing if the user is in a critical MP state.

MP较少时TP获得数

Only Member
– This is how much TP is generated during the Regen TP timing if the user is the only alive member left.

只剩一名玩家存活时TP获得数

Evasion
– This is how much TP is generated whenever the user manages to evade an action performed by another battler.

回避攻击时生成TP数

***
###Notetags
***
You can use the following notetags to adjust the various settings for TP.

你可以使用下面标签来设置TP

####Actor Noretags:

	<TP Mode: x>
This will set the actor’s default TP mode to x. If this notetag isn’t used then the actor will default to the mode within the plugin’s parameters.

设置TP模式

	<Unlock TP Mode: x>
	<Unlock TP Mode: x, x, x>
	<Unlock TP Mode: x to y>
This unlocks what TP modes the actor can use by default. This tag will add upon the default unlocks already preset in the plugin’s parameters.

解锁TP模式

####Skill and Item Notetags:

	<Unlock TP Mode: x>
	<Unlock TP Mode: x, x, x>
	<Unlock TP Mode: x to y>
This will cause the target to unlock TP mode x (to y). This will make the TP mode available in the TP menu.

目标解锁TP模式

####Skill Notetags:

	<Learn Unlock TP Mode: x>
	<Learn Unlock TP Mode: x, x, x>
	<Learn Unlock TP Mode: x to y>
When this skill is learned, unlock TP mode x (to y) in the process of also learning it. This will make the TP mode available in the TP menu.

学习技能时解锁TP模式

***
###Plugin Commands
***
You can use the following Plugin Commands to alter Enhanced TP.

你可以使用下面插件命令来调整TP

####Plugin Command:

	ShowTpMode
	HideTpMode
This will show/hide the TP Mode from the Skill Menu.

显示或隐藏技能菜单的TP模式

	EnableTpMode
	DisableTpMode
This will enable/disable the TP Mode in the Skill Menu.

开启或关闭技能菜单的TP模式

	ChangeTpMode Actor 1 to 5
This will change the TP mode of Actor 1 to TP Mode 5.

改变角色TP模式

	ChangeTpMode Party 2 to 6
This will change the TP mode of Party Member 2 to TP Mode 6.

改变队伍成员TP模式

	UnlockTpMode Actor 3 Mode 7
This will make Actor 3 unlock TP Mode 7.

解锁角色TP模式

	UnlockTpMode Party 4 Mode 8
This will make Party Member 4 unlock TP Mode 8.

解锁队伍成员TP模式

	RemoveTpMode Actor 1 Mode 9
This will make Actor 1 remove TP Mode 9.

移除角色TP模式

	RemoveTpMode Party 2 Mode 10
This will make Party Member 2 remove TP Mode 10.

移除队伍成员TP模式

	UnlockAllTpModes Actor 1
This will make Actor 1 unlock all TP modes.

解锁角色所有TP模式

	UnlockAllTpModes Party 2
This will make Party member 2 unlock all TP modes.

解锁队伍成员所有TP模式

	RemoveAllTpModes Actor 1
This will make Actor 1 remove all TP modes.

移除角色所有TP模式

	RemoveAllTpModes Party 2
This will make Party member 2 remove all TP modes.

移除队伍成员所有TP模式

***
###Happy RPG Making!

