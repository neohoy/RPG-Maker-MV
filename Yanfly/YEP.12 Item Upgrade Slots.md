## YEP.12 – Item Upgrade Slots
This plugin requires the Item Core plugin as this plugin is an extension plugin for it. This plugin enables your players to be able to uprade their weapons and armors through a dedicated slot system.

这个插件需要物品核心插件，这个插件可以让你能够改进物品和装备。
***
###Introduction
***

This plugin requires YEP_ItemCore.
Make sure this plugin is located under YEP_ItemCore in the plugin list.

插件需要YEP_ItemCore，确保插件位于其下面

This plugin adds Item Upgraders, where you can select the base item and then apply the appropriate Item Upgraders onto it to boost its parameters.

这个插件添加了物品提升系统，你可以选择基础物品，然后提升等级

***
###Notetags
***

The following notetags can be used to modify item upgrades.

下面的标签可以用来调整提升等级

####Weapon, and Armor Notetags
	<Upgrade Slots: x>
This sets the number of times an item can be upgraded instead of the default amount defined in the database.

设置物品提升的数量

	<Slot Variance: x>
This makes it so that there is a random variance for the number of slots provided through the item. If this notetag isn’t used, it will go by the setting in the parameters.

提供不同的提升数值，如果没有使用这个标签，则采用插件参数的值

	<Upgrade Sound: filename>
Changes the upgrade sound played to ‘filename’. If this notetag isn’t used, the ‘Default Sound’ parameter sound will be used instead.

改变提升物品时播放的声音。如果没有使用这个标签，则会采用默认声音

	<Upgrade Effect>
	effect
	effect
	</Upgrade Effect>
These are the effects applied (in the order they’re listed). Refer to the ‘Upgrade Effects List’ in the next section to have those effects applied to the upgraded item.

物品提升的影响。这里有一个提升列表，可以应用

	<Upgrade Item Type: All>
	<Upgrade Item Type: Regular>
	<Upgrade Item Type: Key>
	<Upgrade Item Type: Hidden A>
	<Upgrade Item Type: Hidden B>
	<Upgrade Item Type: Always>
	<Upgrade Item Type: Battle>
	<Upgrade Item Type: Menu>
	<Upgrade Item Type: Never>
	<Upgrade Item Type: string>
This makes it so this item can be used to upgrade the item that matches either the item type or the item occassion. If none of those work for you, you can use the following notetag and place an instance for ‘string’ inside of the item upgrade types.


	<Type: string>
Puts this type into the notebox for items (not weapons nor armors) and it will add ‘string’ as its type. You can insert multiple copies of this notetag to enable the item to have more types. Any types in here that match the types for the previous notetag will enable the item to be upgradeable by that upgrade item type.

	<Upgrade Weapon Type: x>
	<Upgrade Weapon Type: x, x, x>
	<Upgrade Weapon Type: x through x>
This makes it so that only weapon types x can use this item for upgrade. If you use weapon type 0, all weapons can be upgraded using this item.

	<Upgrade Armor Type: x>
	<Upgrade Armor Type: x, x, x>
	<Upgrade Armor Type: x through x>
This makes it so that only armor types x can use this item for upgrade. If you use armor type 0, all armor can be upgraded using this item.

***
###Upgrade Effects List
***

The following is a list of effects you can use for the <Upgrade Effects> notetag to have it apply the desired effects to the upgraded item.

####Effect Text Upgrade Effect:

Base Name: x
Changes item’s base name to x. *Note2

Boost Count: +x
Increases Boost Count by x. *Note2

Boost Count: -x
Decreases Boost Count by x. *Note2

Eval: x
Runs x as a piece of code. *Note2

Name: x
Changes item’s name to x. *Note2

Icon: x
Changes item’s icon to x. *Note2

Prefix: x
Changes item’s prefix to x. *Note2

Priority Name: x
Sets priority name to x. *Note2

Random Stat: x
Increases or decreases ‘Stat’ by 0 to x. *Note1

Random Stat: +x
Increases ‘Stat’ by 0 to x. *Note1

Random Stat: -x
Decreases ‘Stat’ by 0 to x. *Note1

Reset Base Name
Resets the base name to default.

Reset Boost Count
Resets the Boost Count to 0.

Reset Icon
Resets the icon back to the default icon.

Reset Prefix
Resets name prefix to default.

Reset Stat
Resets ‘Stat’ back to base stat values. *Note1

Reset Suffix
Resets name suffix to default.

Reset Full
Resets every single aspect about item. *Note3

Slots: x
Changes the slot consumption cost to x. *Note1

Stat: +x
Increases ‘Stat’ by x. *Note1

Stat: -x
Decreases ‘Stat’ by x. *Note1

Suffix: x
Changes item’s suffix to x. *Note2

Note1: ‘Stat’ is to be replaced by ‘MaxHP’, ‘MaxMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, ‘LUK’, ‘SLOTS’, ‘ALL’ or ‘CURRENT’. ‘ALL’ affects all stats. ‘CURRENT’ affects only non-zero stats. This effect will also increase the boost count (+x) by 1 and update the item’s name.

Note2: This does not alter boost count nor update the item’s name unless it is altered by the effect.

Note3: Because this effect resets absolutely everything about an item, it will send the player away from the upgrade menu to reset the standings of the item.

***
###Plugin Commands
***

The following are some Plugin Commands you can use for your game regarding the upgrade option in the item menu:

####Plugin Command:

ShowItemUpgrade
Shows the upgrade option in the item menu.

HideItemUpgrade
Hides the upgrade option in the item menu.

DisableItemUpgrade
Disables the upgrade option in the item menu.

EnableItemUpgrade
Enables the upgrade option in the item menu.

You can use those Plugin Commands at any time to adjust the upgrade option.

***
###Happy RPG Making!

