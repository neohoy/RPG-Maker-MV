##YEP.29 – Party System
***
###Introduction
***

This plugin replaces the “Formation” command found in the in-game menu with a new scene where the player can adjust the party he or she wants in a more comfortable way.

这个插件替代了编队命令，并用一个新的窗口代替，在这里你可以更加方便的调整队伍

If you are using YEP_BattleEngineCore.js and would like to enable party switching mid-battle, place this plugin under YEP_BattleEngineCore.js in the plugin’s list.

如果你使用了YEP_BattleEngineCore，并且想在战斗中开启队伍切换，请把它放在YEP_BattleEngineCore下面

This plugin is plug and play. All you have to do is just turn it on and change the parameters to your liking.

这个插件是即插即用。你只需要打开它并且更改你想要的参数

***
###Plugin Commands
***

Here are some plugin commands you can use!

这里是你需要的一些插件命令

####Plugin Command:

	OpenPartyMenu
Opens up the Party Menu from the field.

打开队伍菜单

Actors can also be required, meaning the player must have that actor(s) in the party before the player is able to leave the party menu. Required actors can be moved around, unlike locked actors. Keep in mind if you do make some actors required, do not make the game require more actors than the possible maximum battle members or else the player will be stuck in the party menu.

在你离开队伍菜单时，你必须拥有至少一名角色。和锁定角色不同，必需的角色可以移动。记住如果你设置了必需的角色，则不要让必需角色数超过战斗队伍最大上限，否则玩家将会卡死在队伍菜单

####Plugin Command:

	ShowBattleFormation
Shows ‘Formation’ command in battle.

在战斗中显示编队命令

	HideBattleFormation
Hides ‘Formation’ command in battle.

在战斗中隐藏编队命令

	EnableBattleFormation
Enables ‘Formation’ command in battle.

在战斗中开启编队命令

	DisableBattleFormation
Disables ‘Formation’ command in battle.

在战斗中关闭编队命令

	LockActor 3
Locks actor 3.

锁定角色3

	LockActor 4 5 6
Locks actors 4, 5, and 6.

锁定角色4，5，6

	UnlockActor 3
Unlocks actor 3.

解锁角色3

	UnlockActor 4 5 6
Unlocks actors 4, 5, and 6.

解锁角色4，5，6

Locked Actors cannot be moved out of their current position and must be in the party.

锁定的角色不可以被从初始位置移开并且必需在队伍里

	RequireActor 3
Player must have actor 3 in party.

必需角色3

	RequireActor 4 5 6
Player must have actors 4, 5, and 6 in party.

必需角色4，5，6

	UnrequireActor 3
Player no longer needs actor 3 in party.

不在必需角色3

	UnrequireActor 4 5 6
Player no longer needs actors 4, 5, and 6 in party.

不在必需角色4，5，6

Required Actors must be in the party in order for the player to be able to exit the party menu.

必需角色必需在队伍里才可以退出队伍菜单

***
###Happy RPG Making!