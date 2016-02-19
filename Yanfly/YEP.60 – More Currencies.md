##YEP.60 – More Currencies

***
###Introduction
***

This plugin requires YEP_ShopMenuCore. Make sure this plugin is located under YEP_ShopMenuCore in the plugin list.

这个插件需要YEP_ShopMenuCore。确保这个插件在YEP_ShopMenuCore之下。

As an extension of the Shop Menu Core, this plugin enables you to have items cost multiple currencies or different currencies using variables and/or other items themselves.

作为商店菜单插件的拓展插件，可以让你通过变量或者物品有更多的货币

***
###Instructions – Variables as Currency
***

If you’re planning to use variables as currency (and you should!), you can set them up in a way to have them show an icon. Name your currency variable as such:

如果你想使用变量作为货币，你需要这样设置他们

	\i[x]Variable Name

When displayed in shops, it will show the icon and the name. However, if you want it to display only the icon and/or exclude some text, place the text inside a << and >> bracket like such:

当显示在商店的时候，它会显示图标和名字。如果你希望只显示图标，可以用《》来隐藏

	\i[x]<<Variable Name>>

That way, only the icon will be shown while all the next inside the << >> will be hidden.

这个方法，只有图标显示，在《》内的文本被隐藏

***
###Instructions – Proxies
***

Perhaps in your game, you would like for the player to have multiple ways of purchasing an item through one currency or another. However, inputting the costs for all of the options makes the item cost every single aspect. But, what you can do is make proxies of these items. For example, in the database will will have the following:

在游戏里，你玩家用不同的货币有很多购买方式。对于所有选项重新设置很麻烦。你可以使用物品代理功能，例如，数据库内这样写

	Potion – 50 Gold
	Potion (Proxy A) – 5 Gems
	Potion (Proxy B) – 3 Jewels

Placing all three items in your shop normally would result in three types of potions that do not stack into the same category. However, by using this proxy notetag, you can make them all attribute to the same Potion item:

如果简单把这3个物品放入商店，将会产生3种相同类型的物品。可以，使用代理标签，你可以设置为一个物品

	<Proxy Buy: x>
	<Proxy Buy: name>
If you’re using this item as a proxy for another item (so you can set a different cost for the item), this item will end up representing item x, weapon x, or armor x of the same type. If you’re using a named notetag and you have multiple entries in your database with the same name, priority will be given to the item, weapon, or armor with the highest ID.

如果你使用了物品代理，这个物品将会代表物品x,武器x,或者装备x。如果你使用了名字标签，你可以代替名字相同的物品，优先选择最高ID物品。

If Proxy A and B link back to the main Potion, then whenever the player buys the Proxies in the shop, they will link back to the main Potion, making it possible to buy the same item using different currencies.

如果代理A和代理B返回主物品，玩家可以通过商店购买代理从而得到主物品，让其实现不同货币来购买同一物品。

***
###Notetags
***

You can use the following notetags to adjust various properties for more currencies for your items, weapons, and armors.

你可以使用下面的标签来调整货币

####Item, Weapon, and Armor Notetags:

	<Variable x Buy Price: y>
This sets the currency of this item, weapon, or armor to variable x with a buy price of y. You can insert multiples of this notetag to have more than one variable cost for that item, weapon, or armor.

设置变量x来购买，价格为y，你可以插入多个标签来获得多个变量货币来购买物品

	<Variable x Sell Price: y>
This makes it that when selling this item, weapon, or armor, the player will gain variable x in y amount. You can insert multiples of this notetag to have more than one variable cost for that item, weapon, or armor.

设置变量x来出售，价格为y，你可以插入多个标签来获得多个变量货币来出售物品

	<Item x Buy Price: y>
	<Item name Buy Price: y>
This sets the currency of this item, weapon, or armor to cost item x (or the named item) with a buy price of y. You can insert multiples of this notetag to have more than one item cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置物品x来购买，数量为y，你可以插入多个标签来获得多个物品货币来购买物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Item x Sell Price: y>
	<Item name Sell Price: y>
When selling this item, weapon, or armor, the player will get item x (or the named item) with a quantity of y. You can insert multiples of this notetag to have more than one item cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置物品x来出售，数量为y，你可以插入多个标签来获得多个物品货币来出售物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Weapon x Buy Price: y>
	<Weapon name Buy Price: y>
This sets the currency of this item, weapon, or armor to cost weapon x (or the named weapon) with a buy price of y. You can insert multiples of this notetag to have more than one weapon cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置武器x来购买，数量为y，你可以插入多个标签来获得多个武器货币来购买物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Weapon x Sell Price: y>
	<Weapon name Sell Price: y>
When selling this item, weapon, or armor, the player will get weapon x (or the named weapon) with a quantity of y. You can insert multiples of this notetag to have more than one weapon cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置武器x来出售，数量为y，你可以插入多个标签来获得多个武器货币来出售物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Armor x Buy Price: y>
	<Armor name Buy Price: y>
This sets the currency of this item, weapon, or armor to cost armor x (or the named armor) with a buy price of y. You can insert multiples of this notetag to have more than one armor cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置装备x来购买，数量为y，你可以插入多个标签来获得多个装备货币来购买物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Armor x Sell Price: y>
	<Armor name Sell Price: y>
When selling this item, weapon, or armor, the player will get armor x (or the named armor) with a quantity of y. You can insert multiples of this notetag to have more than one armor cost for that item, weapon, or armor. If you’re using Item Core, this will not work on independent items. If you are using the named version of the notetag and have multiple items in your database of the same name, priority will be given to the item with the highest ID.

设置装备x来出售，数量为y，你可以插入多个标签来获得多个装备货币来出售物品。如果你使用了物品核心插件，对于独立物品不会生效。如果你使用了名字代码并且有多个重名的物品，将会优先选择ID最高

	<Proxy Buy: x>
	<Proxy Buy: name>
If you’re using this item as a proxy for another item (so you can set a different cost for the item), this item will end up representing item x, weapon x, or armor x of the same type. If you’re using a named notetag and you have multiple entries in your database with the same name, priority will be given to the item, weapon, or armor with the highest ID.

如果你使用物品作为代理，这个物品最后代表物品x,或者武器装备x。如果你使用了名字代码，数据库会优先选择ID最高的

***
###Happy RPG Making!

