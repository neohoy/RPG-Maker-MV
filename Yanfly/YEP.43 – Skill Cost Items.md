##YEP.43 – Skill Cost Items

***
###Introduction
***

This plugin requires YEP_SkillCore.
Make sure this plugin is located under YEP_SkillCore in the plugin list.

这个插件需要YEP_SkillCore，确保它在YEP_SkillCore下面

This plugin enables you to be able to set costs for skills using items. The item costs will appear next to the other skill costs displaying the icons of the items needed and the amount of the items to be used. Item costs using this plugin can be altered by set and percentile amounts in addition to being replaced altogether by a substitute item.

你可以设置技能消耗物品。物品消耗将会显示下次使用技能需要的物品图标和数量。物品消耗可以用这个插件来设置并且可以设置替代品

***
###Notetags
***

To enable skills to utilize items as costs, use the following notetags:

为了能够让技能消耗物品，你需要用下面的标签

####Skill Notetags:
	<Item x Cost: y>
	<Weapon x Cost: y>
	<Armor x Cost: y>
This will set the cost of the item, weapon, or armor x to require y of it before it can be used. If you are using YEP_ItemCore, independent items cannot be used as item costs as the game will not distinguish which of the independent items is fit to be used. If you use multiple of these tags, the skill will require all the listed items to be available for usage.

设置消耗的物品、武器或者装备，需要数量为y。如果你使用了YEP_ItemCore，独立物品不可以被消耗。如果你使用了多个标签，技能需要消耗所有的东西

	<Item Cost: x Potion>
	<Item Cost: x Sword>
	<Item Cost: x Feather Cap>
If you prefer to use the names of the items instead, you can use the above notetag. This will make the skill require x amount of the named item, weapon, or armor. If you have multiple items with the same name, this notetag will give priority to the highest ID value in the order of items, weapons, then armors. If you are using YEP_ItemCore, independent items cannot be used as item costs as the game will not distinguish which of the independent items is fit to be used. If you use multiple of these tags, the skill will require all the listed items to be available for usage.

如果你想要使用物品名字取代，你可以使用这个标签。技能需要x数量的物品。如果你有相同名字物品，优先使用ID最高的。如果你使用了YEP_ItemCore，独立物品不可以被消耗。如果你使用了多个标签，技能需要消耗所有的东西

####Class, Weapon, Armor, State Notetags:
	<Swap Gauge x: Item y>
	<Swap Gauge x: Weapon y>
	<Swap Gauge x: Armor y>
Swaps out gauge x to display how much of item, weapon, or armor y the player/party has. Priority is given in the following order: Weapons, Armors, States, Class, Enemy

显示队伍拥有物品数量的物品槽。优先按照下面顺序：武器、装备、状态、职业、敌人

	<Swap Gauge x: Item Potion>
	<Swap Gauge x: Item Sword>
	<Swap Gauge x: Item Feather Cap>
If you prefer to use the names of the items instead, you can use the above notetag. This will swap out gauge x to display how much of the mentioned item, weapon, or armor the player/party has. If you have multiple items with the same name, this notetag will give priority to the highest ID value in the order of items, weapons, then armors. Priority for the displayed gauge will be given in the following order: Weapons, Armors, States, Class, Enemy.

如果你想使用名字，可以用这个标签。显示队伍拥有物品数量的物品槽。如果你有重名物品，则优先用ID最高的。优先按照下面顺序：武器、装备、状态、职业、敌人

####Actor, Class, Weapon, Armor, and State Notetags:
	<Item x Cost: +y>
	<Item x Cost: -y>
	<Weapon x Cost: +y>
	<Weapon x Cost: -y>
	<Armor x Cost: +y>
	<Armor x Cost: -y>
Increases or decreases the cost of item, weapon, or armor x when required by a value of y. If the item, weapon, or armor isn’t required, then this effect does not apply to the skill cost.

增加或者减少物品、武器或装备消耗。如果物品不被需要，则这个不会生效。

	<Item Cost: +x Potion>
	<Item Cost: -x Sword>
	<Item Cost: +x Feather Cap>
If you prefer to use the names of the items instead, you can use the above notetag format. This will increase or decrease the mentioned item by x amount as long as the item is required as a cost. If you have multiple items with the same name, this notetag will give priority to the highest ID value in the order of items, weapons, then armors.

如果你想使用名字，则用这个标签。增加或者减少物品、武器或装备消耗。如果物品不被需要，则这个不会生效。如果你有重名物品，则优先用ID最高的。

	<Item x Cost: y%>
	<Weapon x Cost: y%>
	<Armor x Cost: y%>
Alters the cost of item, weapon, or armor x by y%. If the item, weapon, or armor isn’t required, then this effect does not apply to the skill cost.

改变物品、武器、装备消耗y%。如果物品不被需要，则不会生效。

	<Item Cost: x% Potion>
	<Item Cost: x% Sword>
	<Item Cost: x% Feather Cap>
If you prefer to use the names of the items instead, you can use the above notetag format. This will adjust the cost rate of the mentioned item by x% as long as the item is required as a cost. If you have multiple items with the same name, this notetag will give priority to the highest ID value in the order of items, weapons, then armors.

如果你想使用名字，则用这个标签。改变物品、武器、装备消耗x%。如果物品不被需要，则这个不会生效。如果你有重名物品，则优先用ID最高的。


	<Replace Type x Cost: Type y>
Replace ‘type’ with either ‘item’, ‘weapon’, or ‘armor’. This lets you exchange the costs used for a particular item for another (item y). The replacement is given priority to states, weapons, armors, class, and then actors.

类型可以是物品、武器或则装备。这个让你改变消耗用的类型。替代优先顺序是状态、武器、装备、职业，然后是角色

	<Replace Potion Cost: Ether>
	<Replace Sword Cost: Dagger>
	<Replace Feather Cap Cost: Bandana>
If you prefer to use the names of the items instead, you can use the above notetag format. This lets you exchange the costs used for a particular item for another. The replacement is given priority to states, weapons, armors, class, and then actors. If you have multiple items with the same name, this notetag will give priority to the highest ID value in the order of items, weapons, then armors.

如果你想使用名字，则用这个标签。这个让你改变消耗用的类型。替代优先顺序是状态、武器、装备、职业，然后是角色。如果你有重名物品，则优先用ID最高的。

####Item, Weapon, Armor Notetags:
	<Item Gauge Color 1: x>
	<Item Gauge Color 2: x>
If this item is the item used as gauge display, you can have it produce a unique color using text color x.

如果物品有显示槽，可以改变显示槽颜色

	<Item Gauge Text: x>
If this item is the item used as gauge display, you can have it show a different text other than its name. Replace x with what you want to write.

如果物品有显示槽，可以改变显示槽文本

	<Item Gauge Text Color: x>
If you wish to use a text color other than the one predefined in the plugin’s parameters, use this notetag and replace x with the text color you wish to label the gauge with.

如果物品有显示槽，可以改变显示槽文本颜色
***
###Happy RPG Making!

