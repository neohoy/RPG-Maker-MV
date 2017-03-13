##YEP.127 – Overkill Bonus – RPG Maker MV
###Introduction

Overkill occurs when an actor defeats an enemy with excessive damage. All enemies have an Overkill damage requirement and if a battler lands a killing blow dealing damage equal to or greater than this number, an animation is played on the enemy before the enemy collapses. When an enemy is overkilled, that enemy will reward the player with more EXP, more gold, a higher drop rate, and if YEP_ExtraEnemyDrops is installed, more possibilities for extra items under the condition of being Overkilled.

当一名角色使用巨大的伤害击败敌人时，我们称之超量杀。所有的敌人都有一个超量杀的值，当玩家击败敌人的伤害大于等于这个值时，会在敌人消失之前播放超量杀的动画。当敌人被超量杀时，会奖励给玩家更多的经验、金币和物品掉落率，如果使用了YEP_ExtraEnemyDrops，在超量杀下额外掉落率会更高

This is a collaboration plugin by Tigress and Yanfly to ensure compatibility with the Yanfly Engine Plugins library.

这个插件是Tigress和Yanfly合作完成，并且适配YEP系列

If you are using YEP_ExtraEnemyDrops, place this plugin underneath that plugin in the plugin manager list to get access to the Overkill condition that is provided within this plugin.

如果你使用了YEP_ExtraEnemyDrops，请把这个插件放在它下面来保障兼容性

###Notetags

Insert the following notetags into the enemy noteboxes you wish to alter the overkill requirements for.

把下面的命令插入敌人的备注栏来改变超量杀的选项

####Enemy Notetags

	<Overkill Requirement: x>
– Changes the enemy’s overkill requirement to X. This is how much damage needs to be dealt minimum on the killing blow. You can use JS code here if you can fit it all on one line. Otherwise, use the notetag setup below in the Lunatic Mode section.

造成超量杀需要的伤害值。这是玩家需要在击败敌人时的最低伤害值。你可以使用JS代码。你也可以在自定义模式里面使用备注设置。

	<Overkill Animation: x>
– This is the animation played when the enemy is overkilled. Replace x with an animation ID from the database.

设置超量杀得动画的ID

	<Overkill EXP Rate: x%>
	<Overkill EXP Flat: x>
– This is the bonus EXP gained when the enemy is overkilled. Replace x with a number value. This EXP gained from overkilling will be added on top of the already gained EXP.

设置超量杀后的经验奖励

	<Overkill Gold Rate: x%>
	<Overkill Gold Flat: x>
– This is the bonus gold gained when the enemy is overkilled. Replace x with a number value. This gold gained from overkilling will be added on top of the already gained gold.

设置超量杀后的金币奖励

	<Overkill Drop Rate: x%>
– This is the bonus drop rate gained when the enemy is overkilled. Replace x with the percent rate increase.

设置超量杀后的物品掉落率

###Extra Enemy Drops Compatibility – Conditional Drop – Overkill

To be used together with the YEP_ExtraEnemyDrops plugin. Place this plugin underneath YEP_ExtraEnemyDrops in the plugin manager list for compatibility. Then, you can use the following condition:

为了和YEP_ExtraEnemyDrops兼容，请置于其下面。你可以使用下面的设置

####IS OVERKILLED

This condition will pass only if the enemy is overkilled. If the overkill requirement isn’t met, there will be no additional changes to the drop rate.

下面的情况仅仅在造成超量杀得时候才会出现，如果不满足条件，则对于掉落率没有任何影响

	Example: Is Overkilled: +100%


One thing you can do to make Overkill only items is using something like the
following setup:

你可以单独设置物品掉落率

	<Conditional Potion Drop>
	is overkilled: +100%
	</Conditional Potion Drop>

This notetag setup will make the ‘Potion’ item only drop if the enemy has been overkilled. Otherwise, nothing will come out of it.

这个备注设置只会让Potion掉落率提高，其他不会改变

###Lunatic Mode – Custom Overkill Settings

This section is for those who wish to dabble with JavaScript a bit more to make certain overkill aspects more customized.

JS代码自定义模式

####Enemy Notetags

	<Overkill Requirement Formula>
	requirement = x;
	<Overkill Requirement Formula>

– Changes the enemy’s overkill requirement to X. This is how much damage needs to be dealt minimum on the killing blow. You can use JS code here if you know how to code. The ‘requirement’ variable is the value that will be used to check if overkill is achieved.

改变超量杀伤害值计算公式

	<Custom Overkill Effect>
	// Insert any code you want here
	</Custom Overkill Effect>

– This code will run when the enemy is overkilled and collapses. The ‘enemy’ variable used here will refer to the enemy itself. The JS code you can use here can be anything you want, including turning on switches, setting variables, anything that comes to mind.

改变超量杀伤害值后的影响效果，例如改变开关，设置变量或者其他

Those who would like to acquire the Overkill image used for the animation from the video can also download it here:

这里提供一个超量杀的图片

Save it and place it into your img/animations/ folder in your RPG Maker project folder.

你可以把它放在img/animations/使用

###Happy RPG Making!

