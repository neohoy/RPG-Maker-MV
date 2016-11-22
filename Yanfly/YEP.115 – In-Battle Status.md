##YEP.115 – In-Battle Status – RPG Maker MV
###Introduction

This plugin requires YEP_BattleEngineCore. Make sure this plugin is located under YEP_BattleEngineCore in the plugin list.

这个插件需要YEP_BattleEngineCore。确保这个插件放在YEP_BattleEngineCore下面

In battle by default, there’s no way to check your party’s status. This plugin will add a new ‘Status’ command to the Party Command Window (with Fight and Escape) to allow players to check party members. Here, the player can view each party member’s current parameters, get a list of all states, buffs, and debuffs. The player can scroll through the list and view newly added help descriptions of the states, buffs, and debuffs in a help window.

在战斗中，我们没有办法查看队伍当前状态，这个插件将会在队伍命令中添加“状态”命令，允许玩家去查看角色状态。在这里，我们可以看到队员的初始参数和状态列表。这个玩家将可以

*Note: If you are using YEP_X_BattleSysCTB.js, place this plugin under that plugin for the best compatibility results.

注意：如果你使用了YEP_X_BattleSysCTB，请把这个插件放在下面以提高兼容性

###Notetags

For those who would like to add help descriptions to states, use these following notetags:

想要添加帮助文字的可以用下面的备注

####State Notetags:

	<Help Description>
	text
	text
	</Help Description>
– This will set the help description of the state to the text used in the notetag. You can use text codes.

这可以添加帮助文字

####Text Codes

By using certain text codes in your messages, you can have the game replace them with the following:

可以使用文本代码

####State Help Function
\th[x] – Replaced by the text used in state x’s help description.

替换为状态帮助文字

###Plugin Commands

For those who would like to change whether the ‘Status’ option is shown or hidden midway through the game, you can use the following plugin commands:

想要改变状态菜单命令的，可以用下面插件来设置

####Plugin Commands:

	ShowInBattleStatus
– This will cause the ‘Status’ command to show.

开启战斗状态命令

	HideInBattleStatus
– This will cause the ‘Status’ command to not show.

关闭战斗状态命令

###Happy RPG Making!


