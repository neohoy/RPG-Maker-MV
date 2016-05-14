##YEP.96 – Item Disassemble
***
###Introduction
***

This plugin requires YEP_ItemCore. Make sure this plugin is located under YEP_ItemCore in the plugin list.

这个插件需要YEP_ItemCore，请放在YEP_ItemCore下面

Sometimes, there are items that are simply not useful to the player anymore. In that case, why not give players the option to break down the item into something a little bit more useful? Using this plugin, players can break down and disassemble items, weapons, and armors into something else. Using different types of disassemblers, the player can get different types of items back, too.

有时候有很多物品道具对玩家没有帮助，在这种情况下，为什么不让玩家选择来分解掉他们获得其他更有用的东西呢？使用这个插件可以分解物品，武器，护甲。使用不同的分解器可以获得不同的物品

***
##Notetags
***

Making items be disassemble-able can be done with these notetags:
使用下面标签让物品具备可分解的属性

####Item, Weapon, and Armor Notetags:

	<Disassemble Pool>
	item
	item
	</Disassemble Pool>
This is the pool of items that will be given when using any disassemblers. Replace the ‘item’ in the notetag setup with one of the syntax in the notetag Item Pool Format list below.

分解后可以获得的物品

	<Disassemble Pool: type>
	item
	item
	</Disassemble Pool: type>
This is the pool of items made specifically for the disassembler type. The items listed in this pool will only drop if the disassembler’s type matches this pool’s type. Replace the ‘item’ in the notetag setup with one of the syntax in the notetag Item Pool Format list below.

设置分解器类型

#####— Item Pool Format —
物品设置格式

	item x
	weapon x
	armor x
	name
– This adds item, weapon, or armor ID x to the disassemble pool. If you plan on using the item’s name and multiple objects in the database have the same name, priority will be given to items, weapons, then armors in that order. Then, priority is then given to the entry with the highest ID.

物品ID或者名字

	item x: y%
	weapon x: y%
	armor x: y%
	name: y%
– If you wish for a chance of getting an item when disassembling instead of a 100% chance of getting it, you can use this format. For the item, there will be a y% chance of getting the item when disassembling.

分解后得到此物品的概率

	x2 item y
	x3 weapon y
	x4 armor y
	x5 name
– When disassembling, items can yield quantities. You can set the amount of an item given when disassembling using this setup.

分解后得到此物品的数量

	x2-3 item y
	x3-5 weapon y
	x5-8 armor y
	x8-10 name
– If you wish for there to be random quantity amounts, you can use this disassembling format to set the amount of quantity given of an item from a minimum amount to a maximum amount.

分解后得到此物品的数量在一个范围内波动

	x2 item y: z%
	x3 weapon y: z%
	x4 armor y: z%
	x5 name: z%
– To make an item yield a larger quantity than 1 with a random success rate of doing it, use the above format for the item line.

分解后得到此物品的数量和概率

	x2-3 item y: z%
	x3-5 weapon y: z%
	x5-8 armor y: z%
	x8-10 name: z%
– To give a random amount of item quantities while having a random success rate of acquiring them item during a disassembling process, use the above item line format.

分解后得到此物品随机数量和概率

—

*NOTE: When turning an item into a Disassembler, it will become a non-Independent item.

注意：当把一个物品设置为分解器时，他就不是独立物品了

	<Disassembler>
– This item can be used to disassemble all types of items. This will fall under the ‘All’ category.

设置为分解器

	<Disassembler: +x%>
	<Disassembler: -x%>
– This item can be used to disassemble all types of items with a +/- x% success rate than normal. This will fall under the ‘All’ category.

改变分解器概率

	<Disassembler: type>
– This item can be used to disassemble item categories for ‘All’ and ‘type’ where ‘type’ is the disassemble pool type. Insert multiples of this notetag if you want this item to be able to disassemble more pool types.

设置分解器类型

	<Disassembler: type +x%>
	<Disassembler: type -x%>
– This item can be used to disassemble item categories for ‘All’ and ‘type’ where ‘type’ is the disassemble pool type. This has a success rate change of +/-% than normal. Insert multiples of this notetag if you want this item to be able to disassemble more pool types.

设置特定分解器类型的分解成功率

	<Disassemble Sound Name: filename>
	<Disassemble Sound Volume: x>
	<Disassemble Sound Pitch: x>
	<Disassemble Sound Pan: +x> or <Disassemble Sound Pan: -x>
– When this item is disassembled, it will play this sound effect. The filename is case sensitive. Do not include the filename extension.

分解时播放的声音设置

***
###Lunatic Mode – Custom Disassembled Effect
***

For those with JavaScript experience, you can have custom effects occur when an item is disassembled using the following notetag:

自定义模式

####Item, Weapon, and Armor Notetags:

	<Custom Disassembled Effect>
	if (targetItem.name === ‘Great Sword’) {
	results.push($dataItems[1]);
	} else if (effectItem.name === ‘Salvage Kit’) {
	results.push($dataItems[2]);
	}
	</Custom Disassembled Effect>
– The ‘results’ variable is an array that contains all of the items that have been collected. The variable ‘targetItem’ refers to the item being disassembled and ‘effectItem’ refers to the item disassembling the target item. This will occur before any custom disassembler effects.

自定义分解器和分解物品的效果

*NOTE: This requires that item to have items to gain when disassembling to begin with or else the item cannot be disassembled.


***
###Lunatic Mode – Custom Disassembler Effect
***

For those with JavaScript experience, you can have custom effects occur when an item is used to disassemble using the following notetag:

自定义模式

####Item, Weapon, and Armor Notetags:

	<Custom Disassembler Effect>
	if (targetItem.name === ‘Great Sword’) {
	results.push($dataItems[1]);
	} else if (effectItem.name === ‘Salvage Kit’) {
	results.push($dataItems[2]);
	}
	</Custom Disassembler Effect>
– The ‘results’ variable is an array that contains all of the items that have been collected. The variable ‘targetItem’ refers to the item being disassembled and ‘effectItem’ refers to the item disassembling the target item. This will occur after any custom disassembled effects.

自定义分解器效果

*NOTE: This item is required to have a disassembler type.

***
###Plugin Commands
***

You can use the following plugin commands to alter Item Disassemble related aspects of your game:

插件命令

####Plugin Command:

	ShowItemDisassemble
– Shows the Disassemble command in the item menu if the item permits disassembling.

显示菜单中的分解命令

	HideItemDisassemble
– Hides the Disassemble command in the item menu regardless.

隐藏菜单中的分解命令

***
###Happy RPG Making!