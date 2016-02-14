##YEP.63 – Weapon Animation
***
###Introduction
***

Ever wanted to give your swords different images despite being the same sword type? Or how about your axes? Or any weapon? Now you can! On top of that, you can even use custom images to accomplish this.

你是否希望给你的剑不同的图像尽管他们是一种类型的剑。或者是你的斧子？或者任何武器？现在你可以了。在这里，你可以自定义图像。

Note: If you are using the YEP_BattleEngineCore, YEP_X_AnimatedSVEnemies, or any of the Action Sequence Packs, place this plugin under those plugins in the plugin list within the Plugin Manager for the best compatibility.

注意：如果你使用了YEP_BattleEngineCore,YEP_X_AnimatedSVEnemies或者其他动作序列，需要把这个插件放在他们后面。

***
###Notetags
***

For those who would like to give their weapons a little bit of a change, you can make use of these notetags:

对于那些想对你的物品做出改变的人，你可以使用下面标签

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Weapon Image: x>
Replace x with a number above 0 and you’ll get an image from img/system’s weapon sheets. Each sheet contains 12 weapon images. If you wish to load a weapon from the first sheet, it’ll be within 1-12. If you wish to load a weapon from the second sheet, it’ll be within 13-24, and so on. The weapon sheets increase in increments of 12, which means that if you wish to load a weapon from weapon sheet 50, x will be between 589 to 600.

用大于0的数代替x，然后你可以从你的img文件夹中获得图像。每一个完整部分包含12个武器图像。如果希望载入第一个部分的物品，他可能在1-12之间。如果你希望从第二部分载入，他可能在13-24之间等等。这个每次增长值为12，这意味着如果你想要武器从第50部分获得，x位于589到600之间。

By default, these are the number values associated with each:

默认，有下面的值参考

>1 - Dagger    7 - Long Bow    13 - Mace        19 - Slingshot   25 - Book  	
2 - Sword     8 - Crossbow    14 - Rod         20 - Shotgun     26 - Custom	  
3 - Flail     9 - Gun         15 - Club        21 - Rifle       27 - Custom
4 - Axe      10 - Claw        16 - Chain       22 - Chainsaw    28 - Custom  
5 - Whip     11 - Glove       17 - Sword#2     23 - Railgun     29 - Custom  
6 - Staff    12 - Spear       18 - Iron Pipe   24 - Stun Rod    30 - Custom  

>1 - 匕首       7 - 长弓      13 - 杖             19 - 弹弓      25 - 书  
2 - 剑         8 - 十字弓    14 - 棍        20 - 猎枪      26 - 自定义  
3 - 枷  9 - 火枪      15 - 也是棍棒 21 - 狙击枪    27 - 自定义  
4 - 斧         10 - 爪       16 - 链子           22 - 锯        28 - 自定义  
5 - 鞭子       11 - 手套     17 - 剑#2           23 - 轨道炮    29 - 自定义  
6 - 棒  12 - 矛       18 - 钢管           24 - 电击棒    30 - 自定义  

	<Weapon Image: filename>
If you have created a custom folder to place unique weapon sheets, you can use this notetag to acquire them. The filename is case sensitive. Do not include the file extension. If your weapon sheet is called DaggerBlue.png, then the notetag you’d use would be `<Weapon Image: DaggerBlue>` only.

如果你创建了一个文件放置自定义武器部分，你可以使用这个标签来获得路径。这个名字不需要带有拓展名。例如你的物品部分叫做DaggerBlue.png，你可以使用这个命令

	<Weapon Motion: thrust>
	<Weapon Motion: swing>
	<Weapon Motion: missile>
This will dictate the motion the battler will use when attacking if you’re using a custom weapon animation. If nothing is placed here, the motion will default to the ‘Default Motion’ value in the plugin parameters. You can use any of the following motions:

当你使用自定义武器动画时，你可以这些来描述动作，你过没有设置，动作将会采用插件中的默认值

> 行走(walk)    等待(wait)     吟唱(chant)    防御(guard)        伤害(damage)  躲避(evade)  
刺(thrust)    挥舞(swing)    投掷(missile)  技能(skill)        咒语(spell)   物品(item)  
逃跑(escape)  胜利(victory)  濒死(dying)    异常状态(abnormal) 睡眠(sleep)   死亡(dead)  

	<Weapon Hue: x>
For those who would like to use different hues with your weapon animation, use this notetag in the same notebox as the <Weapon Image: x> notetag to change the hue of the weapon animation to x.

对于想使用不同颜色的动画的人，可以用这个标签来改变色调

	<Weapon Animation: x>
If you would like to override the attack animation when using this weapon, you can use x to dictate which animation will be used for regular attacks.

如果想优先设置动画，你可以用x来设置动画

If you haven’t noticed yet, these notetags are made for actors, classes, enemies, weapons, armors, and also states. What this means is, the weapon animation changes will behave more like traits. Priorities will occur in the following order:

如果你没有设置标签，这些标签会自动执行。这就意味着，动画将会像特性一样。

>States  
Weapons  
Armors  
Classes  
Actors  
Enemies  

This means that if a battler is affected by a state that would modify its weapon appearance, any other weapon animation changes that the user would have will be overwritten by the state’s weapon animation change until the state wears off.

这意味着，如果战斗者如果被一个改变武器的状态影响，动画将会改变直到状态消失

***
###Instructions – Custom Weapon Images
***

The weapon sheet format will follow RPG Maker MV’s weapon sheet format in individual frame dimensions. However, unlike RPG Maker MV’s weapon sheet format. That said, these custom weapon images will need to be made a certain way in order to look properly with RPG Maker MV’s default battlers.

这个武器部分格式将会遵从软件默认方式。但是，不像默认的武器部分格式，这些自定义图像需要被明确定义使其可以在默认战斗里面正确显示

Here is the weapon sheet format:

这里有一个武器部分格式

>Sheet Width: 288  
Sheet Height: 64  
Frame Width: 96  
Frame Height: 64  

As long as you make them in that format, the weapon sheets will work with RPG Maker’s default battlers.

只要这样设置，就可以战斗中正确生效

***
###And last but not least! The Beam Swords!
***
Here they are! Be sure to save them into the img/weapons/ folder!

这里有一些图像，你可以把他们放入img/weapons/文件夹

And for those who would like to download the entire package: click here.

这些可以在网站下载到

***
###Happy RPG Making!

