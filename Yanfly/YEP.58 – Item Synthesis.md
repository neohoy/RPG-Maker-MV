##YEP.58 – Item Synthesis

***
###Introduction
***

Item synthesis is now a pretty common aspect of most RPG’s where the player can craft their own items after acquiring recipes. This plugin enables your players to be able to do that after acquiring the said recipes. Recipes can come in the form of items, weapons, and/or armors and transcribed in them are what items, weapons, and/or armors they can make. These items can be made from the main menu and/or synthesis locations!

物品合成系统是大多数角色扮演游戏常见的方面，玩家可以通过制作书合成他们自己的物品。这个插件让玩家实现这个功能。制作书可以涉及物品，武器或者装备，并且可以合成物品，武器或者装备。这些物品可以从主菜单或者合成菜单制作。

***
###Notetags
***

To allow the player the ability to craft a certain item, that item must be included in a recipe notetag in an item that the player possesses.

为了让玩家打造出某个物品，这些物品必须拥有制作书的标签

####Item, Weapon, and Armor Notetags:
	<Item Recipe: x>
	<Item Recipe: x, x, x>
	<Item Recipe: x to y>
This will change this item into a recipe for x item(s). As long as this item is in possession by the party as a whole, item(s) x can be synthesized by the player provided that the player has the proper quantity of ingredients.
* Note: Entries without names will not be included. Entries without both a synthesis cost and without an ingredient list will not be included.

可以把这些物品放入制作书，只要队伍拥有这个物品，他就可以被玩家和其他原料一起合成

	<Weapon Recipe: x>
	<Weapon Recipe: x, x, x>
	<Weapon Recipe: x to y>
This will change this item into a recipe for x weapon(s). As long as this item is in possession by the party as a whole, weapon(s) x can be synthesized by the player provided that the player has the proper quantity of ingredients.

可以把这些武器放入制作书，只要队伍拥有这个武器，他就可以被玩家和其他原料一起合成

Note: Entries without names will not be included. Entries without both a synthesis cost and without an ingredient list will not be included.

注意：没有名字的条目，以及没有合成消耗和合成原料列表的条目都不会参与合成

	<Armor Recipe: x>
	<Armor Recipe: x, x, x>
	<Armor Recipe: x to y>
This will change this item into a recipe for x armor(s). As long as this item is in possession by the party as a whole, armor(s) x can be synthesized by the player provided that the player has the proper quantity of ingredients.

可以把这些装备放入制作书，只要队伍拥有这个装备，他就可以被玩家和其他原料一起合成

Note: Entries without names will not be included. Entries without both a synthesis cost and without an ingredient list will not be included.

注意：没有名字的条目，以及没有合成消耗和合成原料列表的条目都不会参与合成

	<Synthesis Ingredients>
	item id
	item id: x
	weapon id
	weapon id: x
	armor id
	armor id: x
	gold: x
	named item
	named item: x
	</Synthesis Ingredients>
Using the above tag in an item will set those items as the ingredients required for the player to synthesize. Replace “id” with the proper item, weapon, or armor ID’s. If no “:x” is used, the database will register that as only needing 1 of that item as an ingredient. If “gold: x” is used, that will be the cost required to synthesize the item.

使用这个标签，可以让物品通过这些原料合成。替代ID即可。如果没有指定ID，数据库认为只需要任何一件物品作为原料即可。如果金钱被指定，则需要消耗如此数量金钱来合成物品

If you are using named entries, priority will be given to the highest ID in the order of items, weapons, then armors.

如果你使用名字，则会优先使用ID最高的

Note: If you are using Item Core, Independent Items cannot become an ingredient for a recipe and will therefore be automatically omitted.

注意：如果你使用了物品核心插件。独立物品不能成为合成原料，将会自动被漏掉

	<Mask Name: x>
If you are masking unknown items’ names, you can change the text shown for the unknown item with x. This will cause the game to use the mask name instead of the usual ??? (if that’s what you’re using) to mask the item. This can give a player a general idea of what they may be synthesizing such as “Strange Liquid” or “Weird Crystal”.

如果你伪装了物品名字，你可以改变物品显示的文本。这将造成游戏采用伪装名代替平时使用的。这可以让玩家生成他们想要的合成品例如“奇异水”或者“特殊水晶”等

***
###Plugin Commands
***

The following are Plugin Commands you may use with events.
下面的插件命令可以使用在事件里面

####Plugin Command:

	OpenSynthesis
Opens up the Synthesis Scene from the field.

打开合成界面

	ShowSynthesis
Shows the Synthesis command from the main menu.

主菜单显示合成命令

	HideSynthesis
Hides the Synthesis command from the main menu.

主菜单隐藏合成命令

	EnableSynthesis
Enables the Synthesis command from the main menu.

开启主菜单合成命令

	DisableSynthesis
Disables the Synthesis command from the main menu.、、
关闭主菜单合成命令

***
###Happy RPG Making!

