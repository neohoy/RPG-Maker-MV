##YEP.53 – Shop Menu Core

***
###Introduction
***

The shop menu in RPG Maker MV is the same as it was in RPG Maker VX and RPG Maker VX Ace. It’s relatively basic and provides adequate information, but not really enough to let the player know what they’re actually buying or even selling. This plugin enables shops to show more than just the basic information displayed in RPG Maker MV and even allows for custom commands to be inserted into the command window.

商店菜单在MV里面和VX、 VX ACE里面相同。它提供基础的信息，但是不足以让玩家知道他们真正想买或者卖什么。这个插件可以让商店显示更多信息，甚至允许自定义命令来插入命令窗口

This plugin also gives the player the option to tab between a parameter comparison mode with the whole party displaying individual stats at a time or individual actors displaying all stats at a time. The player can switch between the two modes by pressing the ‘tab’ button on the keyboard or with touch input on the name of the actor or parameter.

这个插件允许玩家开启一个窗口，可以让队伍成员显示单独的状态或者显示整个队伍的所有人的某个状态。玩家通过tab键开关这个模式或者点击玩家名字

***
###Instructions
***

You can add and remove commands from the Command Window by changing the ‘Command Order’ parameter. Here is a list of commands you may use:

你可以添加或者移除命令，通过命令顺序参数。这里是你可以使用的命令列表

	Buy
– This is the buy item command.

购买命令

	Sell
– This is the sell item command.

卖出命令

	Equip
– This is the equip command to directly access an actor’s equipment.

装备命令

	Custom
– If you have any custom shop menu items, they will be displayed here.

自定义命令

	Cancel
– This exits the shop.

退出商店

***
###Notetags
***

You can use the following notetag to alter various shop aspects

你可以使用下面的标签来改变很多方面

####Item, Weapon, and Armor Notetag:

	<Price: x>
This notetag allows you to exceed the default editor limit for item prices of 999,999 gold.

设置价格，不再受999，999的金钱限制

	<Sell Price: x>
This sets the selling price of the item to x.

设置卖出价格

	<Cannot Sell>
This makes it so that the item cannot be sold.

物品不可以出售

	<Can Sell>
This makes it so that the item can be sold even if it is at 0 gold.

即便价格为0，仍然可以卖出

***
###Happy RPG Making!

