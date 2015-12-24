## YEP.32 Class Change Core
This plugin creates a system where your player can change classes through the main menu allowing for more customization!

这个插件可以让你通过主菜单改变角色职业或级别来实现用户定制需求，进而创造一个伟大的游戏系统

***
- ###Introduction
***

This plugin adds the ability for your player to freely change the classes of actors outside of battle from a menu. When changing classes, this script gives the option for the developer to choose whether or not classes have their own levels (causing the actor’s level to reset back to the class’s level) or to maintain the current level.

这个插件将赋予你的游戏角色在战斗之外，通过菜单更改职业的能力。当改变职业的时候，这个脚本可以让游戏开发者选择是否为他们的职业设定自己专属的等级（这将造成角色等级重置为职业等级）或者保持现有的等级

***
- ### Notetags
***

The following are some notetags you can use with the Class Change Core plugin.

下面是一些你可以利用这个插件使用的标签

#### Actor Notetags:

角色标签

	<Unlock Class: x>
	<Unlock Class: x, x, x>
	<Unlock Class: x to y>
	
> This actor will have class(es) x unlocked at the start of the game in addition to its current class and access to any of the global classes.

> 这个角色将会在游戏开始或者进行当中的时候解锁这些职业

	<Class x Character: filename y>
	
> When this actor’s class is x, the actor’s character sprite will become ‘filename’ and index y on the fieldmap.

> 当游戏角色的职业ID是x的时候，游戏角色画面将成为图片y

	<Hero Character: filename y>
	<Warrior Character: filename y>
	
> If you prefer to use class names instead of the class ID, use the above format. When this actor is this class, the actor’s character sprite will become ‘filename’ and index y on the fieldmap.  

> 如果不想使用职业ID，而是采用名字，可以使用这段代码。当游戏角色处于设定职业的时候，他的游戏角色画面将成为图片y

	<Class x Face: filename y>
	
> When this actor’s class is x, the actor’s face graphic will become ‘filename’ and index y for menus.

> 当角色职业ID为X的时候，他的游戏角色面部图片将成为y

	<Hero Face: filename y>
	<Warrior Face: filename y>
	
> If you prefer to use class names instead of the class ID, use the above format. When this actor is this class, the actor’s face graphic will become ‘filename’ and index y for menus.

> 如果不想使用职业ID，而是采用名字，可以使用这段代码。当游戏角色处于设定职业的时候，他的游戏角色面部画面将成为图片y

	<Class x Battler: filename>

> When this actor’s class is x, the actor’s battler sprite will become ‘filename’ in battle.

> 当角色职业ID为X的时候，他的游戏角色战斗图片将成为y

	<Hero Battler: filename>
	<Warrior Battler: filename>
	
> If you prefer to use class names instead of the class ID, use the above format. When this actor is this class, the actor’s battler sprite will become ‘filename’ in battle.

> 如果不想使用职业ID，而是采用名字，可以使用这段代码。当游戏角色处于设定职业的时候，他的游戏角色战斗画面将成为图片y

#### Class Notetags: 

	<Icon: x>
	
> Sets the icon for this class to x. This icon is used in the Class Change menu listing.

> 设置职业图标，这个图标将应用于职业菜单列表中

	<Help Description>
	Text
	Text
	</Help Description>
	
> Sets the help description for the class to the specified text.

> 设置职业的自定义介绍

	<Level Unlock Requirements>
	Class x: Level y
	Class x: Level y
	</Level Unlock Requirements>

> Sets the requirements for unlocking that particular class. The unlocking of the class will require classes x to be at level y. Insert multiple of the strings in between the two opening and closing notetags to require all of the class levels to be met.

> 设置解锁特定职业的等级。职业x将在角色处于等级y的时候开启。可以在开启和关闭的标签之内插入这串代码，就可以匹配所以的职业等级


	<Level Unlock Requirements>
	Hero: Level y
	Warrior: Level y
	</Level Unlock Requirements>
	
> If you prefer to use class names instead of the class ID, use the above format. This will set the level requirement for the mentioned class to y. If there are multiple classes with the same name, the class with the highest ID value will be taken.

> 如果你想要使用职业名字来替代职业ID，可以使用以上这段代码。对于的特定的职业，我们可以设置他的等级需求为y。如果存在多个相同名字的职业，将会匹配ID最高的。

***
- ### Plugin Commands
***

> Included in this plugin are multiple Plugin Commands to help assist you with class changing for your game.

> 在这个插件里面，我们集成了很多插件命令来帮助你改变游戏设计。

#### Plugin Command
	
	OpenClass
	
> This opens the class changing scene.

> 打开职业变更窗口

	ShowClass
	
> This shows the Class option from the main menu.

> 显示主菜单职业选项

	HideClass
	
> This hides the Class option from the main menu.

> 隐藏主菜单职业选项

	EnableClass
	
> This makes the Class option enabled.

> 打开职业选项

	DisableClass
	
> This makes the Class option disabled.

> 关闭职业选项

	UnlockClass 5 6
	
> This allows Actor 5 to unlock Class 6.

> 允许角色5解锁职业6

	RemoveClass 5 7
	
> This causes Actor 5 to no longer access Class 7.

> 允许角色5不能使用职业7

	UnlockClassAll 8
	
> This unlocks Class 8 for the global pool.

> 为所有人解锁职业8

	RemoveClassAll 9
	
> This removes Class 9 from the global pool.

> 为所有人移除职业9

***

## Happy RPG Making!

