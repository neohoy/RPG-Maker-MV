##YEP.119 – Weak Enemy Poses – RPG Maker MV

###Introduction

This plugin requires YEP_BattleEngineCore. Make sure this plugin is located under YEP_BattleEngineCore in the plugin list.

这个插件需要YEP_BattleEngineCore，确保放在YEP_BattleEngineCore下面

Non-animated enemies often appear lifeless. They maintain one appearance throughout the whole battle and do not change it under any circumstances. This plugin allows you to set different images for enemies when they are under certain health percentages as well as other conditions.

无动画的敌群经常很无趣味，他们在整个战斗过程中保持一个姿势不曾改变。这个插件允许你设置不同的敌群图片，例如不同的血量显示不同的图片等等

###Notetags

Insert the following notetags into the database entries’ noteboxes to alter the weak pose data.

把这些备注插入数据库敌群备注栏

####Enemy Notetags:

	<x% Health Pose: filename>
– At x% HP or lower, the enemy will use ‘filename’ for its battler image instead of its default one. The filename is case sensitive and must not include the file extension. Insert multiple of these notetags to give the enemy various poses across different health values. NOTE: This applies only to static enemies and NOT animated enemies.

当血量低于x%时，敌人会显示自定义图片。文件名不包含文件拓展名。你可以插入多个语句来设置不同的血量显示不同的图片。注意：这个仅限于静态敌人，不可以使用带有动画的敌人。

	<x% Health Pose: filename, hue>
– At x% HP or lower, the enemy will use ‘filename’ for its battler image instead of its default one and a different hue instead of its default. The filename is case sensitive and must not include the file extension. The hue must be a value between 0 and 360. Insert multiple of these notetags to give the enemy various poses across different health values.NOTE: This applies only to static enemies and NOT animated enemies.


当血量低于x%时，敌人会显示自定义图片和自定义血量条。文件名不包含文件拓展名。颜色则介于0-360之间。你可以插入多个语句来设置不同的血量显示不同的图片。注意：这个仅限于静态敌人，不可以使用带有动画的敌人。

####State Notetags:

	<Force Enemy Pose: filename>
– When an enemy is afflicted with this state, the enemy would take on this battler image as long as that state is the highest priority state with a forced enemy pose. Replace ‘filename’ with the battler image to be used. The filename is case sensitive and must not include the file extension.NOTE: This applies only to static enemies and NOT animated enemies.

当敌方处于此状态，敌方将会显示这个自定义图片。

	<Force Enemy Pose: filename, hue>
– When an enemy is afflicted with this state, the enemy would take on this battler image as long as that state is the highest priority state with a forced enemy pose. Replace ‘filename’ with the battler image to be used. The filename is case sensitive and must not include the file extension. The hue must be a value between 0 and 360.NOTE: This applies only to static enemies and NOT animated enemies.

当敌方处于此状态，敌方将会显示这个自定义图片和自定义颜色。

###Lunatic Mode – Custom Enemy Poses

For those with JavaScript experience, you can alter the pose used for an enemy (static only, not animated) using these Lunatic Mode notetags:

自定义模式

####Enemy Notetags:

	<Custom Enemy Pose>
	if (user.mpRate() >= 0.50) {
	name = ‘Scorpion’;
	hue = 180;
	} else {
	name = ‘Spider’;
	}
	</Custom Enemy Pose>
– The ‘name’ variable will refer to the filename used for the battler image. The filename is case sensitive and must not include the file extension. If the ‘hue’ variable is used, then that hue will be forced. Otherwise, it will use the default hue of the enemy. The hue must be a value between 0 and 360.NOTE: This applies only to static enemies and NOT animated enemies.


####State Notetags:

	<Custom Enemy Pose>
	if (user.mpRate() >= 0.50) {
	name = ‘Scorpion’;
	hue = 180;
	} else {
	name = ‘Spider’;
	}
	</Custom Enemy Pose>
– When an enemy is afflicted with this state, the enemy would take on the ‘name’ image as long as that state is the highest priority state with a forced enemy pose. The filename is case sensitive and must not include the file extension. If the ‘hue’ variable is used, then that hue will be forced. Otherwise, it will use the default hue of the enemy. The hue mustbe a value between 0 and 360.NOTE: This applies only to static enemies and NOT animated enemies.

For the other variable to use:

	defaultBattlerName
– This will be the default battler’s name.

默认战斗者图片名字

	defaultBattlerHue
– This will be the default battler’s hue.

默认战斗者图片颜色

###Happy RPG Making!