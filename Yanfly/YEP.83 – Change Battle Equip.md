##YEP.83 – Change Battle Equip
***
###Introduction
***

This plugin requires YEP_BattleEngineCore and YEP_EquipCore. Make sure this plugin is located under YEP_BattleEngineCore and YEP_EquipCore in the Plugin Manager’s plugin list.

这个插件需要 YEP_BattleEngineCore和YEP_EquipCore。确保放在这两个底下

This plugin enables your player to be able to switch out an actor’s equips mid-battle. This will take the player to the Equip menu rather than leave the player inside the battle scene.

这个插件可以让你在战斗中切换装备。
***
###Notetags
***

Use the following notetags to alter how the Change Battle Equip command functions for your actors in battle.

使用下面标签来设置

####Actor, Class, Weapons, Armors, and State Notetags:

	<Change Battle Equip Cooldown: +x>
	<Change Battle Equip Cooldown: -x>
Increases or decreases the number of turns an actor has to wait in battle before the actor can change equips again by x amount.

改变战斗装备冷却

	<Disable Change Battle Equip>
This will disable the ability to change equipment mid-battle for the related actor.

关闭改变战斗装备能力

***
###Happy RPG Making!

