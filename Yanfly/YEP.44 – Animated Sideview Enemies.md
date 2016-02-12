## YEP.44 – Animated Sideview Enemies

This plugin requires Battle Engine Core. This extension plugin allows you to animate enemies in a number of ways, from giving static enemies breathing, floating, and scaled attributes to utilizing animated sideview actors as potential battlers for your enemies instead of static graphics to help make your enemies appear more lively!

此插件需要前置插件Battle Engine Core。这个扩展插件可以让敌人变得栩栩如生，其方式可以是让静态的敌人呼吸、飘浮，或者赋予敌人可动的侧面战斗图像来代替静态的图片，这会使敌人看上去更活泼！

***
### Introduction
***
介绍

This plugin requires YEP_BattleEngineCore.
 Make sure this plugin is located under YEP_BattleEngineCore in the plugin list.

此插件需要前置插件YEP_BattleEngineCore。请确保此插件在插件列表中位于YEP_BattleEngineCore的下方。

This extension plugin allows you to animate enemies in a number of ways, from giving static enemies breathing, floating, and scaled attributes to utilizing animated sideview actors as potential battlers for your enemies instead of static graphics to help make your enemies appear more lively!

此个扩展插件可以让敌人变得栩栩如生，其方式可以是让静态的敌人呼吸、飘浮，或者赋予敌人可动的侧面战斗图像来代替静态的图片，这会使敌人看上去更活泼！

If you are using YEP_X_ActSeqPack2, and would like the ability to add in floating enemies, place this plugin under YEP_X_ActSeqPack2 as well.

如果你也在使用YEP_X_ActSeqPack2，并且想要把它的功能加入飘浮敌人中，那么也需要把此插件放在YEP_X_ActSeqPack2的下面。

To use this plugin, insert within the enemy’s notebox the notetags you see in the section below:

使用此插件的方法是在敌人的注释栏中输入下述的注释。

***
### Notetags
***
注释

Insert these notetags into the enemy noteboxes below to change their sidewview battler aspects.

在敌人注释栏内输入下面的注释来改变它们的侧面战斗外貌。

#### Enemy Notetags:

敌人的注释：

— General —

— 通用 —

	<Breathing>
	<No Breathing>
	
 Enables or disables a ‘breathing’ effect for the enemy sprite.

对敌怪使用或禁止使用“呼吸”效果。

	<Breathing Speed: x>
	
 How many frames does it take to make a full breathing cycle? The lower the x value, the faster the enemy breathes. The higher the x value, the slower the enemy breathes.

需要多少帧来完成一次完整的呼吸动作？x的值越小，敌人呼吸得越快；x的值越大，敌人呼吸得越慢。


	<Breathing Rate X: x.y>
	<Breathing Rate Y: x.y>
	
 Sets the horizontal and vertical breathing rate to x.y. 1.0 is a 100% variance change while 0.0 is a 0% variance.

将呼吸动作的水平及竖直幅度设为x.y。设为1.0将是100%的变化幅度，而0.0是0%的变化幅度。

	<Floating>
	
 Sets the enemy to be animated as if it was floating.

使敌人的活动就像在飘浮。

	<Floating Speed: x>
	
 How many frames does it take to do a full floating cycle? The lower the x value, the faster the enemy floats. The higher the x value, the slower the enemy floats.

需要多少帧来完成一次完整的飘浮动作？x的值越小，敌人飘浮得越快；x的值越大，敌人飘浮得越慢。

	<Floating Rate: x.y>
	
 Sets the floating rate for the enemy to x.y. 1.0 is a 100% variance change while 0.0 is a 0% variance change.

将飘浮动作的幅度设为x.y。设为1.0将是100%的变化幅度，而0.0是0%的变化幅度。

	<Floating Height: x>
	
 Sets the minimum float height for the enemy to x.

设置敌人飘浮的最小高度为x。

	<Scale Sprite: x%>
	
 This allows you to scale the sprite larger or smaller by x% of the original sprite size. If you wish to only scale either the width or the height, use the notetags below:

改变怪物的尺寸，将原始尺寸变大（或变小）x%。如果你只想改变宽度或高度，可以用下述注释：

	<Scale Sprite Width: x%>
	<Scale Sprite Height: x%>
	
 This will scale the sprite’s width or height by x% amount specifically rather than the whole sprite itself by the same ratio.

将怪物的宽度或高度改变x%，而不是按相同比例改变整个怪物的大小。

— Sideview —

— 侧面视图 —

<Sideview Battler: filename>
 This is the filename used for the sideview battler found within your project’s img/sv_actors/ folder. Doing this will enable the following notetags to be applied to the battler. This is case-sensitive and used without the image’s file extension.

此注释指明了在文件夹img/sv_actors/中的用于侧视战斗图的文件名，使用之后才能应用下述注释于战斗图。文件名的输入不必包含文件扩展名，但要区分大小写。

*Example: SF_Actor3_8.png would be <Sideview Battler: SF_Actor3_8>
 *Note: If more than one of these tags is used, the sideview battler selected will be picked from a random pool. Their settings, however, will match all of the other sideview settings set in the notetags for the sake of simplicity.

*例：SF_Actor3_8.png应输入为<Sideview Battler: SF_Actor3_8>
*注意：如果使用了多个这样的注释，那么侧视战斗图将会从中随机选取。而它们的设定将同样会满足注释栏中其它的侧视设置。

— Sideview Specific —

— 侧面视图详细设定 —

	<Sideview Anchor X: y.z>
	<Sideview Anchor Y: y.z>
	
 This sets the anchor location for the enemy’s sideview battler at y.z. This is used for the event you have an odd-proportioned sideview battler.

设置敌人侧视战斗图的原始位置为y.z。可用于侧视战斗图的比例很奇特的情形。

	<Sideview Width: x>
	<Sideview Height: x>
	
 Sets the width/height of the sideview battler. This is for the event you’re using a battler image that may have different proportions than normal sideview battlers.

设置侧视战斗图的宽度/高度。可用于侧视战斗图的比例与正常战斗图的比例不同的情形。

	<Sideview Collapse>
	
 Sets it so that the enemy when it dies will collapse and vanish.

使敌人在死亡时瓦解并消失。

	<Sideview No Collapse>
	
 Sets it so that the enemy when it dies will leave behind a corpse and will not vanish.

使敌人在死亡时留下尸体而不会消失。

	<Sideview Frame Speed: x>
	
 Sets the frame speed of this sideview battler to x. The lower the x value, the faster the sideview battler animates. The higher it is, the slower the battler animates.

设置此侧视战斗图的帧速度为x。x的值越小，侧视战斗图动得越快；x的值越大，侧视战斗图动得越慢。

— Motions —

	<Sideview Attack Motion: swing>
	<Sideview Attack Motion: thrust>
	<Sideview Attack Motion: missile>
	
 Sets the basic attack motion for your sideview enemy if the sideview enemy is not using any weapons. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为没有武器的敌人的侧视图设置基本的攻击动作。你可以使用下述任意动作：

> 行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)

	<Sideview Weapon: x>
	
 This sets the sprite’s weapon image to x. If you haven’t modified your system images of the weapons, they would be as follows:

> 0 - Nothing  
1 - Dagger  7 - Long Bow 13 - Mace      19 - Slingshot 25 - Book  
2 - Sword   8 - Crossbow 14 - Rod       20 - Shotgun   26 - Custom  
3 - Flail   9 - Gun      15 - Club      21 - Rifle     27 - Custom  
4 - Axe    10 - Claw     16 - Chain     22 - Chainsaw  28 - Custom  
5 - Whip   11 - Glove    17 - Sword#2   23 - Railgun   29 - Custom  
6 - Staff  12 - Spear    18 - Iron Pipe 24 - Stun Rod  30 - Custom  

设置精灵的武器图像为x。如果你没有修改过系统的原始武器图片，那么对应方式如下：
> 0 - 无  
1 - 匕首       7 - 长弓      13 - 杖             19 - 弹弓      25 - 书  
2 - 剑         8 - 十字弓    14 - 棍(rod)        20 - 猎枪      26 - 自定义  
3 - 枷(flail)  9 - 火枪      15 - 也是棍棒(club) 21 - 狙击枪    27 - 自定义  
4 - 斧         10 - 爪       16 - 链子           22 - 锯        28 - 自定义  
5 - 鞭子       11 - 手套     17 - 剑#2           23 - 轨道炮    29 - 自定义  
6 - 棒(staff)  12 - 矛       18 - 钢管           24 - 电击棒    30 - 自定义  

 Note: Inserting multiple of these notetags will put them inside a random pool of weapons to use. Keep in mind if you use this notetag, it will use all the default settings found in the plugin’s parameters. If you wish to use more unique settings, use the notetag below:

请注意：若输入多个这样的注释，那么武器图像将会从中随机选取。需要记住的是，此注释将使用插件参数中的默认设置。如果你想用更独特的设置，使用下面的注释：

	<Sideview Weapon: x, y, z>
	
 This sets the sprite’s weapon image to x, motion to y, and attack animation to z. An example of how this notetag would be used would be as such:

设置精灵的武器图像为x，动作为y，而攻击动画为z。例如：

	<Sideview Weapon: 2, swing, 6>

This will give the battler a sword with the swing motion and playing battle animation 6 when attacking.

给战斗图一把挥动的剑，并在战斗时播放战斗动画6。

	<Sideview Idle Motion: x>
	
 Sets the idling motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置等待（idling）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

 Note: Inserting multiple of these notetags will put them inside a random pool of motions to use.

 请注意：若输入多个这样的注释，那么动作将会从中随机选取。

	<Sideview Damage Motion: x>
	
 Sets the damaged motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置受伤（damage）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Evade Motion: x>
	
 Sets the evasion motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

 为侧视敌人设置躲避（evasion）动作。可以使用下述动作：
 
>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Escape Motion: x>
	
 Sets the escaping motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置逃跑（escaping）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Guard Motion: x>
	
 Sets the guard motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置防御（guard）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Abnormal Motion: x>
	
 Sets the abnormal motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置异常状态（abnormal）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Sleep Motion: x>
	
 Sets the sleep motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置睡眠（sleep）动作。可以使用下述动作：

> 行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Dying Motion: x>
	
 Sets the dying (crisis) motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置濒死（dying/crisis）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Sideview Dead Motion: x>
	
 Sets the dead motion for your sideview enemy. You can use any of the following motions:
walk   wait    chant   guard    damage evade
thrust swing   missile skill    spell  item
escape victory dying   abnormal sleep  dead

为侧视敌人设置死亡（dead）动作。可以使用下述动作：

>行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

— Shadows —

— 阴影 —

	<Sideview Show Shadow>
	
 Sets it so the enemy will show its shadow for its sideview sprite. The default setting of this is tied to Battle Engine Core’s ‘Show Shadows’.

使敌人的侧视精灵显示阴影。此注释的默认设置依赖于Battle Engine Core的“Show Shadows”。

	<Sideview Hide Shadow>
	
 Sets it so the enemy will hide its shadow for its sideview sprite. The default setting of this is tied to Battle Engine Core’s ‘Show Shadows’.

使敌人的侧视精灵隐藏阴影。此注释的默认设置依赖于Battle Engine Core的“Show Shadows”。

	<Sideview Shadow Width: x%>
	
 Sets the shadow width to x% larger/smaller than the default shadow size found within the img/system folder.

令阴影宽度与文件夹img/system中的默认阴影尺寸相比增大/减小x%。

	<Sideview Shadow Height: x%>
	
 Sets the shadow height to x% larger/smaller than the default shadow size found within the img/system folder.

令阴影高度与文件夹img/system中的默认阴影尺寸相比增大/减小x%。

#### State Notetags:

状态的注释：

	<Hide Sideview Weapon>
	
 This will cause the animated sideview enemy battler to hide its sideview weapon effect. The attack motion will revert back to the barehanded attack motion set for the enemy and the attack animation will be the enemy’s default attack animation.

使动态侧视战斗图隐藏侧视武器效果。敌人的攻击动作将会变回空手的攻击动作，攻击动画会变成敌人的默认攻击动画。

***

### Happy RPG Making!
