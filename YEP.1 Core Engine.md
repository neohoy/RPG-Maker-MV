## YEP.1 Core Engine
Yanfly Engine Plugins is a plugin library made for RPG Maker MV, a wonderful piece of software to help you make that role playing game of your dreams. You can find out more about RPG Maker MV here.  
 
【】Yanfly引擎是一个为PRG Maker MV制作的插件库，它是一个很棒的软件，可以用来帮你制作你自己梦想的游戏。你可以在这里找到很多关于RPG Maker MV的东西

The Core Engine plugin is a plugin that’s made to address the core aspects of your game project, from raising the limits of stats to changing the colors of your window objects. Also to be included with this plugin will be any bug fixes made for RPG Maker MV. This plugin will be periodically updated whenever there is a new bug that is fixed.  

这个引擎插件的核心就是致力于处理游戏项目的核心方面，从提高游戏状态的限制到改变你窗口的颜色。同时通过这个插件，我们也会修复一些软件上的错误。只要有新的错误出现，这个插件会定期更新来修复

Yanfly Engine Plugins’ Core Engine is not a requirement for the plugin library to work.  

Yanfly引擎插件的核心对于插件库来说不是必须的  

***
- ### Introduction and Instructions
***

Yanfly Engine Plugins – Core Engine is made for RPG Maker MV. This plugin functions primarily to fix bugs and to allow the user more control over RPG Maker MV’s various features, such as the screen resolution, font, window colors, and more.

Yanfly引擎插件的核心引擎是为RPG Maker MV制作的。这个插件的功能主要是修复错误和允许用户对于软件特性有更多的控制，例如屏幕显示，字体，窗口颜色等等。

Just place this on top of all the other Yanfly Engine Plugins.

把这个引擎放在其他Yanfly插件的上面

Adjust any parameters as you see fit.

调整你需要更改的参数即可

***
- ### Gold
***

You can use the plugin commands to add or remove gold more than the editor’s 9,999,999 limit. You can also place notetags into items, weapons, and armors to over the 999,999 cost limit.  

你可以使用这个插件命令来改变游戏内金钱9，999，999的上限。你也可以改变其他项目999，999的限制，例如物品，武器，装备等。 

#### Plugin Command:

插件命令

	GainGold 1234567890

> Party gains 1234567890 gold.

> 队伍获得1234567890金钱

	LoseGold 9876543210
	
> Party loses 9876543210 gold. 
 
> 队伍丢失9876543210金钱

#### Item, Weapon, Armor Notetags

物品，武器，装备标签

	<Price: x
> Changes the price of the item to x. This notetag allows you to bypass the editor’s 999,999 gold cost limit.

> 可以改变物品的价格，这个标签允许你超过编辑器999，999的限制。

#### Enemy Notetag

敌方备注

	<Gold: x

> Changes the gold drop value of enemies to x. This notetag allows you to bypass the editor’s 9,999,999 gold drop limit.

> 可以改变消灭敌人掉落的奖励，这个标签允许你超过编辑器999，999的限制。

***
- ### Items
***

Change the parameters to reflect the maximum number of items a player can hold per item. If you wish to make individual items have different max values, use the following notetag:

可以改变一个玩家可以携带物品的最大数量。如果你希望每个物品有不同的最大值，你可以使用下面的标签。

#### Item, Weapon, Armor Notetag:

物品，武器，装备标签

	<Max Item: x
	
> This changes the maximum amount of the item to x.

> 这个可以改变物品的最大数量

***
- ### Stats
***

Even with the parameter limits raised, the editor is still confined to RPG Maker MV’s default limits. To break past them, use the following notetags to allow further control over the individual aspects for the parameters.

事件参数的限制的提升，我们可以对编辑器默认的限制操作。为了解除限制，我们可以使用下面的标签来获得对参数的更高控制权。

#### Actor Notetag

角色标签

	<Initial Level: x
	
> Changes the actor’s initial level to x. This allows you to bypass the editor’s level 99 limit.

> 改变角色的初始等级。这可以让你突破99级的限制。

	<Max Level: x
	
> Changes the actor’s max level to x. This allows you to bypass the editor’s level 99 limit.

>  改变角色的最大等级。这可以让你突破99级的限制。

#### Class Skill Learn Notetag

技能学习标签

	<Learn at Level: x
	
> When placed inside a class’s “Skills to Learn” notetag, this will cause the class to learn the skill at level x.

> 当这个标签被放入技能标签栏的时候，你可以让玩家在相应等级习得此技能

#### Weapon and Armor Notetags

武器和装备标签

	<stat: +x
	<stat: -x
	
> Allows the piece of weapon or armor to gain or lose x amount of stat. Replace “stat” with “hp”, “mp”, “atk”, “def”, “mat”, “mdf”, “agi”, or “luk” to alter that specific stat. This allows the piece of equipment to go past the editor’s default limitation so long as the maximum value allows for it.

> 这可以让武器或者装备能够失去或者获得某些状态。例如你可以替换stat状态为hp血量，mp蓝量，atk攻击，def防御，mat魔攻，mdf魔防，agi速度，luk幸运等。这将允许装备属性超过编辑器的默认值，只要符合最大允许范围

#### Enemy Notetags

敌方标签

	<stat: x

>T his changes the enemy’s stat to x amount. Replace “stat” with “hp”, “mp”, “atk”, “def”, “mat”, “mdf”, “agi”, or “luk” to alter that specific stat. This allows the piece of equipment to go past the editor’s default limitation.

> 这将改变敌方的状态。例如你可以替换stat状态为hp血量，mp蓝量，atk攻击，def防御，mat魔攻，mdf魔防，agi速度，luk幸运等。这将允许装备属性超过编辑器的默认值，只要符合最大允许范围

	<exp: x
	
> This changes the enemy’s exp given out to x amount. This allows the enemy give out more exp than the editor’s default 9,999,999 limit.

> 这将改变消灭敌方的经验值。它允许玩家得打超过编辑器默认9，999，999的更高经验值

***

## Happy RPG Making!



