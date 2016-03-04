##YEP.45 – Swap Enemies
***
###Introduction
***

This plugin allows you to have an enemy be a basic randomizing swap dummy for other enemies. Insert enemy ID’s of other enemies inside of the swap notetag and those enemies will take place of the swap monster at the start of a battle.

这个插件可以让你的敌人变换外形。插件其他敌人ID在标签栏，这个敌人就会在战斗开始变换

***
###Notetags
***

The purpose of swap enemies is to make it easier to swap out enemies for a random enemy inside of a particular pool of enemies. Use the following notetags to utilize this plugin:

敌人变换的目的是为了更好地在敌人池里面变出随机敌方。你可以使用下面的标签来设置

####Enemy Notetag:
	<Swap: x, x, x>
	<Swap: x to y>
Changes this enemy into a swap dummy. Replace x with the ID’s of the other enemies you would like to randomly spawn in its place. Insert multiples of this tag if you wish to add more randomized enemies to the pool.

设置变换为x

	<Swap>
	Slime
	Hornet
	Bat
	Wisp>
	</Swap>
If you wish to use names instead, you can construct your notetags in the above format. Enemies with matching names will be added to the random swap pool for the swap dummy. If you have multiple enemies in the database with the same name, priority will be given to the enemy with the highest ID.

用名字设置的变换对象。如果你有重名对象，则优先ID最高的

***
###Happy RPG Making!