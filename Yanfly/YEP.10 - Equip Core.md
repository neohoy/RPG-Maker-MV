## YEP.10 – Equip Core
The Equip Core plugins makes quite a few changes for your projects. It affects the equip menu, equipment type handling, equipment rulings, and parameter control.

装备核心插件改变了游戏很多选项。将会影响装备菜单，装备类型索引，装备规则等等。

***
### Introduction
***

This plugin alters various aspects regarding equipment handling. The changes are as listed:

插件改变包括如下：

1. Scene_Equip
Scene_Equip has been modified to look differently. This is primarily done to make the main menu scenes look uniform and keep everything familiar for players. Furthermore, the command window has been adjusted to be better fit for extension plugins in the future that may add commands to the command window and/or the scene.  
装备界面：装备界面调整了一下，会略微不同。主要是制作了主菜单让人看起来统一并且对于玩家更加熟悉。更长远来说，命令菜单可以更好的适应未来的拓展插件，以便添加命令

2. Equipment Type Handling
Characters will no longer have one universal equipment slot setting. Now, different classes can use different setups by simply adding a few notetags to the class notebox. Furthermore, equipment types in the past with matching names would be treated as separate types. Now, equipment types with matching names will be treated as the same type.
装备类型：玩家不只有一个通用的设置。现在，不用的职业可以通过简单的标签来添加不同的设置。还有，之前名字一样的装备类型视为不同的类型，现在，名义一样的装备类型归为一类

3. Equipment Rulings
Now, certain equipment types can or cannot be removed. For example, this plugin can set it so that the Weapon slot must always have something equipped and that the player cannot manually leave it empty (the game, on the other hand, can achieve this through events). In addition to that, optimizing equipment can be restricted for certain equipment types, which are better off being decided manually (such as accessories).  
装备规则：现在，装备类型可以被选择能不能移除。例如，这个插件设置了了武器必须装备，所以玩家武器栏不可以为空。除此之外，可选择装备被确定类型限制，最好关闭自动决定。

4. Parameter Control
Equipment parameters can now to be adjusted through notetags to have a large value or customized value (through code). This allows for equipment to no longer be static items, but instead, equipment can now be dynamic and may change over the course of the game.  
参数控制：装备参数可以同标签设置，来自设置一个较大的值或者自定义值。这将允许装备不再是静态物品而是可以通过游戏改变的

***
###Notetags
***

You can use the following notetags to change a class’s equipment setup.

你可以用下面的标签改变职业装备设置

####Class Notetags:
	<Equip Slot: x>
	<Equip Slot: x, x, x>
	
Example:
 
	<Equip Slot: 1, 2, 3, 4, 5, 5, 5, 5>
Changes this class’s equipment slots to x. Using repeating numbers makes it so that equipment type is duplicated and that the class can equip multiple equipment of that type. To find the Equipment Type ID, go to your database’s Types tab and look for the ID type.

例如：改变角色可以装备的类型ID

If you don’t like the above method for setting equipment slots, you can use the following notetags instead:

如果你不喜欢这个方法，你可以用下面方法替代

	<Equip Slot>
	string 
	string
	string
	string
	</Equip Slot>

Example:

	<Equip Slot>
	Weapon
	Armor
	Accessory
	Accessory
	</Equip Slot>
Replace ‘string’ with the Equipment type’s name entry. This is case sensitive so if the string does not match a name entry perfectly, the slot will not be granted to the class. Multiple copies of a name entry would mean the class can equip multiple equipment of that type. Everything works the same as the previous notetag.

用特定的物品类型放入代码即可。

####Weapon and Armor Notetags:
	<stat: +x>
	<stat: -x>
Allows the piece of weapon or armor to gain or lose x amount of stat. Replace “stat” with “hp”, “mp”, “atk”, “def”, “mat”, “mdf”, “agi”, or “luk” to alter that specific stat. This allows the piece of equipment to go past the editor’s default limitation so long as the maximum value allows for it. Changes made here alter the base parameters.
允许武器装备或者或者失去某些值。你可以用血量、魔法值、攻击力、防御力、魔法攻击力、魔法防御力、速度或者幸运值来代替。这将允许装备可以突破默认编辑器的限制。

***
###Lunatic Mode – Custom Parameters
***

	<Custom Parameters>
	code
	code
	code
	code
	</Code Parameters>

Example:

	<Custom Parameters>
	atk = $gameVariables.value(1);
	mat = atk / 2;
	all = $gameParty.members().length;
	</Custom Parameters>

Allows for parameters to have custom rates adjusted by code. The following parameters are defined: ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, and ‘all’. The ‘all’ parameter will affect all parameters. Changes made here do not alter the base parameters, but instead, are added onto the base parameters.

允许玩家自定义参数。

***
###Happy RPG Making!