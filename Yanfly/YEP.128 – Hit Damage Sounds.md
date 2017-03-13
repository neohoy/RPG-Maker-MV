##YEP.128 – Hit Damage Sounds – RPG Maker MV
###Introduction

Different types of armors make different sounds when they’re hit. When an actor is struck by an attack and takes damage, they will play a sound effect based off the armor they are wearing (ie. cloth versus metal). Enemies can also play different sound effects when they get hit, too (ie. slimes versus robots). Use this plugin to make your armors and enemies more lively when they react to damage.

不同的类型的护甲在收到伤害时会发出不同的音效。当玩家遭受攻击并受到伤害时，他们会基于穿戴的护甲播放音效，例如布甲和铁甲。敌人在收到伤害时也可以播放不同的音效，例如粘液或机械。使用这个插件可以让玩家或者敌人在受到伤害时表现的更加活泼。

This is a collaboration plugin by Chickie and Yanfly to ensure compatibility with the Yanfly Engine Plugins library.

这是Chickie和Yanfly共同合作的插件，确保可以适配YEP系列。

###Instructions

Change the plugin parameters to make default hit damage sound effects for specific armor types. These armor types are found in the Database > Types tab found in your RPG Maker MV project’s database. If an armor type is left empty, it will not play a special hit damage sound effect when the actor is struck by a damaging action.

改变插件的参数来设置不同护甲类型的默认音效。护甲类型可以在MV项目中的数据库-类型中找到。如果某个类型为空，则不会播放任何特殊音效。

If the armor has a hit damage sound effect, it will be played. Otherwise, the regular damage sound effect will play. If an actor has multiple pieces of armor with different hit damage sounds, a random sound will be played from that selection of armors.

如果护甲有伤害音效，他就会播放，否则则播放普通音效。如果玩家拥有多件带有特殊音效的护甲，则随机播放其中一个。

Enemies can also play hit damage sound effects when struck, too. However, they can only have one sound effect when being hit.

敌人也可以播放伤害音效，但是他们只可以拥有一种。

###Notetags

Insert the following notetags into the armors and/or enemy noteboxes to make them play different sounds when getting struck.

将下面代码插入护甲或者敌人的备注栏里设置

####Armor and Enemy Notetags

	<Hit Damage Sound: filename>
	<Hit Damage Sound: filename, volume>
	<Hit Damage Sound: filename, volume, pitch>
	<Hit Damage Sound: filename, volume, pitch, pan>
– Makes the piece of armor or enemy play ‘filename’ when struck. When inserting the filename, the filename must be case sensitive and must not include the extension. The ‘volume’ and ‘pitch’ variables must be integar values between 0 and 100 if they are used. The ‘pan’ variable can be an integar value between -100 and 100 if it is used.

设置伤害音效的文件、音量、音调、声场

Examples:

	<Hit Damage Sound: Fire1>
	<Hit Damage Sound: Fire2, 80>
	<Hit Damage Sound: Fire3, 80, 130, 20>

In the above examples, the armor piece or enemy will play the Fire sound effects when struck. This will override the default settings.


###Happy RPG Making!