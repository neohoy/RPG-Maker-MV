##YEP.66 – Steal & Snatch

***
###Introduction
***

Stealing is a commonly used mechanic found in many traditional RPG’s. This plugin enables you to replicate that mechanic and add more depth upon it.

偷窃技能是很多传统RPG都有的技能。这个插件可以让你能够开启这个能力并且更深度的开发了它

Enemies can have multiple items to steal in addition to their default drops. When an actor goes to steal from an enemy, the actor has a percent change for the steal attempt to be successful. If successful, the actor grabs a random item from the stealable items pool and the party gains the said item.

除了默认掉落，敌方有很多东西可以偷窃。当玩家偷窃敌方时，角色会判断成功率。如果成功则随机得到偷窃池内的物品

In addition to stealing, there is a new mechanic called ‘Snatch’. While stealing allows your actors to grab random items from the enemy, snatching lets your actors target the item they want to steal and focus only on that item alone.

除了偷窃，这里还有新的能力叫做抢劫。相比偷窃允许玩家从敌方获得随机物品，抢劫可以让玩家获得你想偷得物品并且强制得到

Another feature for this plugin is that stealing a piece of equipment can now ‘debuff’ the enemy. If an actor steals a sword that gives 10 ATK, the enemy will lose 10 ATK. This feature can be turned off. Also new (and optional) is the ability to steal the enemy’s drop items. Enemies won’t always necessarily drop their items after being defeated, but stealing from them directly will allow your players to secure those items. Once an item is stolen, it will not drop again at the end of battle.

插件的另一个特点就是抢劫装备碎片可以减益敌方。如果角色偷了一把攻击10的短剑，敌方攻击力掉落10。这个功能可以被关闭。敌方不一定会掉落他们的物品，但是偷窃可以确保你拿到。一旦物品被偷，在战斗结束时将不会掉落

***
###Notetags
***

Use the following notetags to set up your steal effects.

使用下面的标签来设置你的偷窃效果

####Enemy Notetags:

	<Steal Item x: y%>
	<Steal Weapon x: y%>
	<Steal Armor x: y%>
	<Steal Gold x: y%>
Gives the enemy the respect item to be stolen. x is the item’s ID while y% is the rate at which the item can be stolen from.

设置可以偷的物品及概率

	<Steal Potion: y%>
	<Steal Short Sword: y%>
	<Steal Round Shield: y%>
If you decide to use names instead of item ID’s, you can use the above notetag format. If you have multiple items with the same name, priority will be given to the item with the highest item ID in the order of items, weapons, and then armors.

使用名称来设置可以偷的物品及概率

	<Steal Resist: +x%>
	<Steal Resist: -x%>
This is the enemy’s inherent resistance against stealing.

防偷能力增加或减少x%

####Skill and Item Notetags:

	<Steal>
	<Steal: +x%>
	<Steal: -x%>
This enables the skill/item to have steal properties. Actions with steal properties will have a chance of stealing an item. This notetag applies to all item types. If you use the notetag versions with +x% or -x%, the steal rate is increased/decreased by x%.

开启技能或者物品的偷窃特性。拥有偷窃特性的行动有机会偷得物品。适用于所有物品类型。你还可以设置物品偷窃概率的增减

	<Steal Item>
	<Steal Item: +x%>
	<Steal Item: -x%>
This enables the skill/item to have steal properties. Actions with steal properties will have a chance of stealing an item. This notetag adds item types to the stealable item pool. If you use the notetag versions with +x% or -x%, the steal rate is increased/decreased for item types by x%.

开启偷窃物品特性，并设定概率

	<Steal Weapon>
	<Steal Weapon: +x%>
	<Steal Weapon: -x%>
This enables the skill/item to have steal properties. Actions with steal properties will have a chance of stealing an item. This notetag adds weapon types to the stealable item pool. If you use the notetag versions with +x% or -x%, the steal rate is increased/decreased weapon item types by x%.

开启偷窃武器特性，并设定概率

	<Steal Armor>
	<Steal Armor: +x%>
	<Steal Armor: -x%>
This enables the skill/item to have steal properties. Actions with steal properties will have a chance of stealing an item. This notetag adds armor types to the stealable item pool. If you use the notetag versions with +x% or -x%, the steal rate is increased/decreased for armor types by x%.

开启偷窃装备特性，并设定概率

	<Steal Gold>
	<Steal Gold: +x%>
	<Steal Gold: -x%>
This enables the skill/item to have steal properties. Actions with steal properties will have a chance of stealing an item. This notetag adds gold types to the stealable item pool. If you use the notetag versions with +x% or -x%, the steal rate is increased/decreased for gold by x%.

开启偷窃物金钱特性，并设定概率

	<Snatch>
	<Snatch: +x%>
	<Snatch: -x%>
This enables the skill/item to have snatch properties. Actions with snatch properties are able to select the exact item they wish to steal. This notetag applies to all item types. If you use the notetag versions with +x% or -x%, the snatch rate is increased/decreased by x%.
Note: Snatching only works on skills/items that target.

开启抢劫特性，并设定概率，只适用于技能或者物品目标

	<Snatch Item>
	<Snatch Item: +x%>
	<Snatch Item: -x%>
This enables the skill/item to have snatch properties. Actions with snatch properties are able to select the exact item they wish to steal. This notetag adds items to the pool. If you use the notetag versions with +x% or -x%, the snatch rate is Note: Snatching only works on skills/items that target.

开启抢劫物品特性，并设定概率，只适用于技能或者物品目标

	<Snatch Weapon>
	<Snatch Weapon: +x%>
	<Snatch Weapon: -x%>
This enables the skill/item to have snatch properties. Actions with snatch properties are able to select the exact item they wish to steal. This notetag adds weapons to the pool. If you use the notetag versions with +x% or -x%, the snatch rate is increased/decreased by x% for weapons.
Note: Snatching only works on skills/items that target.

开启抢劫武器特性，并设定概率，只适用于技能或者物品目标

	<Snatch Armor>
	<Snatch Armor: +x%>
	<Snatch Armor: -x%>
This enables the skill/item to have snatch properties. Actions with snatch properties are able to select the exact item they wish to steal. This notetag adds armors to the pool. If you use the notetag versions with +x% or -x%, the snatch rate is increased/decreased by x% for armors.
Note: Snatching only works on skills/items that target.

开启抢劫装备特性，并设定概率，只适用于技能或者物品目标

	<Snatch Gold>
	<Snatch Gold: +x%>
	<Snatch Gold: -x%>
This enables the skill/item to have snatch properties. Actions with snatch properties are able to select the exact item they wish to steal. This notetag adds gold targets to the pool. If you use the notetag versions with +x% or -x%, the snatch rate is increased/decreased by x% for gold.
Note: Snatching only works on skills/items that target.

开启抢劫金钱特性，并设定概率，只适用于技能或者物品目标

####Item, Weapon, and Armor Notetags:

	<Enable Automatic Debuff>
	<Disable Automatic Debuff>
This let’s you override the ‘Automatic Effect’ settings in the parameters for this individual item. Enabling it will cause any weapons and armors to debuff the enemy’s parameters relative to the piece of equipment stolen. Disabling it will make no such thing occur. Automatic Debuffing is only applied to weapons and armors.

开启和关闭自动减益

	<Steal Sound Name: filename>
If you wish to give an item a unique sound effect when stolen, use this notetag to accomplish that. Exclude file extensions from the ‘filename’.

偷窃声音设置

	<Steal Sound Volume: x>
To change the volume for this item’s sound effect when it is stolen, use this notetag and replace x with the volume level desired.

偷窃声音音量设置

	<Steal Sound Pitch: x>
To change the pitch for this item’s sound effect when it is stolen, use this notetag and replace x with the pitch desired.

偷窃声音音调设置

	<Steal Sound Pan: x>
To change the pan for this item’s sound effect when it is stolen, use this notetag and replace x with the pan desired.

偷窃声音音域设置

####Actor, Class, Weapon, Armor, and State Notetags:

	<Steal Rate: +x%>
	<Steal Rate: -x%>
	<Steal Type Rate: +x%>
	<Steal Type Rate: -x%>
Increase/decrease the steal rate for the user by x%. If you use the ‘Type’ notetag, replace ‘Type’ with ‘Item’, ‘Weapon’, ‘Armor’, or ‘Gold’ to apply individual steal rate bonuses for just those types.

偷窃概率设置

***
###Happy RPG Making!