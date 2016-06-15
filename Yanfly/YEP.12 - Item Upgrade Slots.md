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

这个是你可以提升物品的类型。如果这里面没有你需要的类型，你可以用下面的标签命令来设置。

	<Type: string>
Puts this type into the notebox for items (not weapons nor armors) and it will add ‘string’ as its type. You can insert multiple copies of this notetag to enable the item to have more types. Any types in here that match the types for the previous notetag will enable the item to be upgradeable by that upgrade item type.

可以把你想要的物品类型放入物品标签栏。你可以批量插入标签来获得多个类型。

	<Upgrade Weapon Type: x>
	<Upgrade Weapon Type: x, x, x>
	<Upgrade Weapon Type: x through x>
This makes it so that only weapon types x can use this item for upgrade. If you use weapon type 0, all weapons can be upgraded using this item.

这可以让武器类型中的第x个可以提升。如果是0，则全部都可以。

	<Upgrade Armor Type: x>
	<Upgrade Armor Type: x, x, x>
	<Upgrade Armor Type: x through x>
This makes it so that only armor types x can use this item for upgrade. If you use armor type 0, all armor can be upgraded using this item.

这可以让装备类型中的第x个可以提升。如果是0，则全部都可以。

***
###Upgrade Effects List
***

The following is a list of effects you can use for the <Upgrade Effects> notetag to have it apply the desired effects to the upgraded item.

下面这个影响列表你可以用来应用提升效果

####Effect Text Upgrade Effect:

Base Name: x  
Changes item’s base name to x. *Note2  
基础名字改为x  

Boost Count: +x  
Increases Boost Count by x. *Note2  
增量+x  

Boost Count: -x  
Decreases Boost Count by x. *Note2  
增量+x  

Eval: x  
Runs x as a piece of code. *Note2  
执行代码x  

Name: x  
Changes item’s name to x. *Note2  
物品名字改为x  

Icon: x  
Changes item’s icon to x. *Note2  
图标改为x  

Prefix: x  
Changes item’s prefix to x. *Note2  
前缀改为x  

Priority Name: x  
Sets priority name to x. *Note2  
优先名字改为x  

Random Stat: x  
Increases or decreases ‘Stat’ by 0 to x. *Note1  
增加或者减少状态0到x  

Random Stat: +x  
Increases ‘Stat’ by 0 to x. *Note1  
增加状态0到x  

Random Stat: -x  
Decreases ‘Stat’ by 0 to x. *Note1  
减少状态0到x  

Reset Base Name  
Resets the base name to default.  
重置基础名字  

Reset Boost Count  
Resets the Boost Count to 0.  
重置增量  

Reset Icon  
Resets the icon back to the default icon.  
重置图标  

Reset Prefix  
Resets name prefix to default.  
重置前缀  

Reset Stat  
Resets ‘Stat’ back to base stat values. *Note1  
重置状态  

Reset Suffix  
Resets name suffix to default.  
重置后缀  

Reset Full  
Resets every single aspect about item. *Note3  
重置所以方面  

Slots: x  
Changes the slot consumption cost to x. *Note1  
改变提升消耗  

Stat: +x  
Increases ‘Stat’ by x. *Note1  
增加状态x  

Stat: -x  
Decreases ‘Stat’ by x. *Note1  
减少状态x  

Suffix: x  
Changes item’s suffix to x. *Note2  
改变后缀为x  

Note1: ‘Stat’ is to be replaced by ‘MaxHP’, ‘MaxMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, ‘LUK’, ‘SLOTS’, ‘ALL’ or ‘CURRENT’. ‘ALL’ affects all stats. ‘CURRENT’ affects only non-zero stats. This effect will also increase the boost count (+x) by 1 and update the item’s name.

注意1：状态可以被最大血量，魔法量，攻击，防御等等替代。并且会改变增量和物品名字

Note2: This does not alter boost count nor update the item’s name unless it is altered by the effect.

注意2：这不会改变增量或者物品名字

Note3: Because this effect resets absolutely everything about an item, it will send the player away from the upgrade menu to reset the standings of the item.

注意3：因为重置，会将角色从升级菜单跳出

***
###Plugin Commands
***

The following are some Plugin Commands you can use for your game regarding the upgrade option in the item menu:

下面的插件命令你可以使用

####Plugin Command:

	ShowItemUpgrade
Shows the upgrade option in the item menu.  
显示升级选项

	HideItemUpgrade
Hides the upgrade option in the item menu.  
隐藏升级选项

	DisableItemUpgrade
Disables the upgrade option in the item menu.  
关闭升级选项

	EnableItemUpgrade
Enables the upgrade option in the item menu.  
开启升级选项

You can use those Plugin Commands at any time to adjust the upgrade option.

你可以在任何时候使用插件命令来调整升级选项

***
###Happy RPG Making!

