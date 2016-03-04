##YEP.50 – Buffs & States Core
***
###Introduction
***

If you are using YEP_BattleEngineCore.js, please this plugin under YEP_BattleEngineCore in the plugin list for the best effect.

如果你在使用YEP_BattleEngineCore.js，请放在YEP_BattleEngineCore.js下面

Alter the basic mechanics behind buffs and states that aren’t adjustable within the RPG Maker editor. Such mechanics include altering the maximum number of times buffs can stack, changing the turns remaining on buffs and states, and the rules involved when reapplying states.

这可以改变增益效果和状态。这些包括增益效果持续时间，回合等等

A turn indicator has been added to show the amount of turns remaining on buffs, debuffs, and states. Buffs and debuffs will operate off the plugin parameter settings while states can operate on individual settings if you choose for them to have unique settings.

我们为增益效果、减益效果、状态等添加了一个回合指示器。你可以通过插件参数来设置增益和减益效果，或者也可以用单独的设置来改变状态

Furthermore, a lot of Lunatic Mode options are added with this plugin to allow those with JavaScript proficiency maximum control with states and any unique effects that follow.

并且，有很多自定义模式可以来设置，你可以用JS语言来更好的设置状态或者其他特殊影响

***
###Notetags
***

The following are various notetags you can use to modify states and buffs.

下面这个标签你可以用来调整状态和效果

— Buff Related —

####Actor, Class, Enemy, Weapon, Armor, and State notetags:

	<Max stat Buff: +x>
	<Max stat Buff: -x>
	<Max stat Debuff: +x>
	<Max stat Debuff: -x>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’ without the quotes. This notetag adjusts the maximum number of times the stat can be buffed or debuffed to the Maximum Limit cap in the plugin parameters.

设置状态调整数值

####Skill and Item Notetags:

	<stat Buff Turns: +x>
	<stat Buff Turns: -x>
	<stat Debuff Turns: +x>
	<stat Debuff Turns: -x>
Modifies already applied buff/debuff turns on target by x value. If this brings a buff/debuff to 0 or below, the buff/debuff is removed.

设置持续回合

— State Related —

####State Notetags:

	<Show Turns>
	<Hide Turns>
Show/hide the turn count remaining for the state. This will override the default setting.

显示回合数

	<Turn Font Size: x>
Sets the font size used for this specific state to be x. This will override the default setting.

显示回合数文本大小

	<Turn Alignment: Left>
	<Turn Alignment: Center>
	<Turn Alignment: Right>
This sets the text alignment for the turn count indicator. This will override the default setting.

显示回合数的位置

	<Turn Buffer X: +x>
	<Turn Buffer X: -x>
	<Turn Buffer Y: +x>
	<Turn Buffer Y: -x>
Allows you to adjust the x/y position manually for the turn count for this particular state. This will override the default settings.

调整显示回合数的位置

	<Turn Color: x>
This will set the turn count display color to text color x. This will override the default setting.

显示回合数的文本颜色

	<Reapply Ignore Turns>
	<Reapply Reset Turns>
	<Reapply Add Turns>
Changes the rules when this state is reapplied on a battler. When ignored, the turn count remains unchanged. When reset, the turn count is set back to the default amount with variance. When added, the turn count is added upon with variance.

当状态再次应用时的规则。如果是忽略，则继续计回合数，如果重置，则回合数为默认值，如果叠加，则加到原有回合数上

####Skill and Item Notetags:

	<State x Turns: +y>
	<State x Turns: -y>
	<State named Turns: +y>
	<State named Turns: -y>
Modifies already applied state x turns on target by y value. If this brings the state to 0 or below turns, the state is removed. If you are using named states and have multiple states with the same name, priority will be given to the state with the highest ID.

改变状态持续时间。如果你使用名字来设置，当重名时，优先考虑ID最高的

####Enemy Notetags:

	<Show State Turns>
	<Hide State Turns>
Affected by the Battle Engine Core. When selecting enemies, the state turns will show up in the help window. You can use this to have certain enemies show the state turns or hide them.

显示状态持续回合

***
###Happy RPG Making!