## YEP.11 – Item Core

The Item Core plugin changes a lot of things about your project, from the item menu to independent items. But more importantly, this plugin builds a bridge for those who wish to do more with their items…

物品核心插件改变了游戏的很多内容，从物品菜单到个人包裹，更重要的是这个插件为希望设置更多物品选项的人搭建了桥梁。

>
Hello, I am aware that Independent Items have a “maximum” amount. This “maximum” amount only serves to limit the player from buying too many items and filling up the inventory with junk. Gaining items through any other method, such as events and battle drops are still allowed.  
你们好，我知道私人包裹有最大数量限制。这个最大数量限制只是为了限制玩家购买太多的物品，导致垃圾填满了仓库。你可以用其他方式来获得物品，例如事件，战斗掉落等。
>
Now, why is this? Because not every scenario can be envisioned by the developer. In most cases, the developer can be short sighted and may not be aware of the player’s inventory limits at the time. So, to mitigate this, I made it possible for the player to go above the limit but only through events and battle drops.  
为什么呢？因为开发者不可能考虑所以情况。大多数下，开发者不能知道玩家的仓库容量。所以，为了减轻这种情况，除非有事件或者战斗掉落，否则玩家只能被限制数量。
>
Why those two? Because of key items. Key items, if given by events and/or battle drops, are a necessity to progress in a game. Should the developer be unaware of the player’s inventory and provide a key item that cannot be inserted into the inventory, the player will be locked out of the game through no fault of their own. So to prioritize the player, this system is enabled.  
又为什么呢？因为关键物品。在游戏中，通过事件或者战斗给与关键物品是游戏重要的换届。如果开发者不知道玩家库存，并且提供的关键物品无法进入仓库，玩家将会被锁住游戏进程不能游戏。所以优先考虑玩家，这个系统被打开。
>
Therefore, it is functioning as intended as a way to work as a fail safe for the sake of the player incase of any developer shortsight.  
所以，这是一项对于开发者来说相对安全的措施

***
### Introduction
***

This plugin makes a couple of main changes to your game and the way items handled to allow a base core for future plugins.

这个插件改变了游戏很多主要设置，同时也是未来拓展插件所要依赖的核心插件。

#### 1. Independent Items  
If you choose to have maximum limit on your items, weapons, and/or armors, those items will become independent and have their own individual stats and whatnot. Independent items are capable of being upgraded, altered, modified, etc. and retain those changed properties independent of other items of the same type. Items without a maximum limit (aka 0), they will continue working as they normally did in RPG Maker MV.

如果你想要有物品的最大数量限制，那么这些物品会有独立的统计等。独立的。独立物品可以被提升，改变，修改等同时保留物品类型。没有最大数量限制的物品，他们将会以默认的物品管理方式运行。

#### 2. New Scene_Item
The item scene has been revamped to look a little bit different. With the new layout, the item list is no longer two columns, but one. Added are a few more windows, such as the item status window (which displays basic item information), an item information window (which shows information applied to the item via upgrades, etc.), and an item action window, which appears when you select an item and it will ask you if you wish to Use the item or any action added via plugins (such as upgrading the item). If you wish to not use this revamp, you can disable it from the parameters.

物品界面看起来略微不同。有了分层，物品列表不在是2列，而是一列。并且添加了更多的界面，例如物品重要程度，物品信息，物品动作等。如果你不想使用这个修改，你可以用参数关闭它。

#### 3. Random Variance
Newly acquired items that aren’t from shop can be given randomized stats to a small degree for items that are independent. Items can be above the stock value or below the stock value by the variance value. If you wish for an item to not have a variance value, you can use a notetag to set the variance value to 0. If you wish for all of your items to not have a variance value, you can set the parameter to 0.

不是从商店买来的物品可以一定程度上获得随机属性。数值可以在一个范围内浮动，如果你不希望有浮动，你可以使用标签设置为0.如果你希望所有物品都没有浮动，你可以设置参数为0.

Note: During battle test, independent items are disabled.  
注意：在战斗测试中，个人物品菜单是关闭的。

***
### Notetags
***

If you are using independent items, items that aren’t gained through the shop can have a random variance applied to its stats.

如果你希望使用独立物品，并且有一个随机属性，你可以使用下面标签

####Item, Weapon, Armor Notetag
	<Random Variance: x>
	
If this item is acquired through non-shop means, it will have random stats offset by x amount in either a positive or negative value.

设置随机属性x

	<Not Independent item>
Sets an item that is independent by default to become a nonindependent item, allowing it to stack and making it unable to be affected by independent item modifiers.

非独立物品

	<Priority Name>
This sets the item, weapon, or armor’s priority name to its database entry so that name schemes cannot affect the item.

设置物品的优先名，让数据库内的名字不会影响物品

***
### Plugin Commands
***

If you wish to be able to add items to your player’s inventory without the random variance being applied to it, you can use the following plugin commands to adjust the settings for that.

如果你不希望为你的物品添加随机属性，你可以使用下面的命令改变设置

#### Plugin Command:
	EnableVarianceStock
Causes all items acquired from this point forward to have its variance give stock (nonrandom) values.

开启固定值

	DisableVarianceStock
Causes all items acquired from this point forward to have its variance give random values.

开启随机值

A small note is that if you enabled the variance stock values, if the player restarts the game by either going through the title screen or just turning off the program and starting it back up, the random variance will in effect again. This plugin command is meant to exist short term disable.

有个小提示需要注意，如果你开启了固定值，玩家重新通过游戏标题界面再次进入游戏或者关闭程序重新启动，随机值将会开启。插件命令只是一个暂时的关闭

***
###Eventing Changes
***

A few changes have been made to eventing in order to adjust for independent items. They are as follows:

我们改变了一些事件让其可以调整独立物品。它们是：

####Event Page Conditions and Conditional Branches:
Checking to see if an item exists in the party’s inventory will differ if the item can be independent. Instead, the condition can be fulfilled if there is an item, even when upgraded, that has the selected item as the base item. This means your Long Sword (+1) will fulfill the condition of having the target Long Sword item in the event editor.

条件及分支：当检查你的仓库里是否存在物品时，独立物品的+1属性不会造成影响，可以认为物品存在

####Actor Has X Equip:
Just like the previous condition, this condition will be fulfilled if the actor has a weapon whose base item matches the event editor’s target item. The Long Sword (+1) will fulfill the condition of needing the actor to have a Long Sword item equipped.

装备：当检查你的装备里是否存在物品时，独立装备的+1属性不会造成影响，可以认为物装备存在

####Change Equipment:
If the target equipment is independent, the game will first check to see if the actor has an item equipped with the matching base item. If not, the game will then check to see if the party has a matching base item in the inventory first and use that. If not, then the game will create a new stock version of the item and equip that to the actor.

装备改变：如果装备标签是独立物品，这个游戏会检查基础装备来适配，如果没找找到，则会检查个人仓库；如果依旧没有，则会创建一个类别。

***
### Item Name System
***

For independent items, they have a unique name handling system. Independent items consist of four parts:

对于独立物品，他们有一个特殊的名字索引系统。包括如下：

####Prefix Base Name Suffix Boost Count

The prefix, base name, suffix, and boost count are adjusted by plugins. Depending on the effects applied, they can be altered or changed. Using the name system, an item with a prefix of ‘Fiery’, base name of ‘Sword’, suffix being ‘of Might’, and a boost count of 5 will end up looking like:

前缀，名字，后缀，增量可以用插件来调整。如下便是一个例子：前缀Fiery，名字Sword，后缀of Might，增量5.

#####Fiery Sword of Might (+5)

These item would appear that way only if its various name parts have been altered some way or another. However, there is a fifth name convention, and that is the priority name. If an item has a priority name, it will completely overwrite the current name scheme with just the priority name itself. So even if the item’s name is ‘Fiery Sword of Might (+5)’, if the item’s priority name is ‘Legendary Blade’, then ‘Legendary Blade’ will take priority.

如果设置了其他名字，则不会显示带有前后缀增量的名字
***
###Lunatic Mode – Custom Info Window Display
***

If you want to display unique and custom stuff into your info window on the side, you can use the following notetags:
如果你想自定义一些选项，可以使用如下：

####Item, Weapon, Armor Notetags:

	<Info Text Top>
	text
	text
	</Info Text Top>
Type in extra information you wish to type in for the item info window here, whether it is lore or other information. Text codes can be used. Information here is is displayed towards the top of the info window.

顶部显示文字

	<Info Text Bottom>
	text
	text
	</Info Text Bottom>
Type in extra information you wish to type in for the item info window here, whether it is lore or other information. Text codes can be used. Information here is is displayed towards the bottom of the info window.

底部显示文字

	<Info Eval>
	var variableId = 1;
	var value = 500;
	$gameVariables.setValue(variableId, value);
	</Info Eval>
If you know JavaScript, you can use these notetags to run some code before displaying any new info. This way, if you plan on using text codes that display variable values, you can run a bit of code before displaying them to synch up what’s shown in the item info window.

显示自定义信息

***
### Happy RPG Making!

