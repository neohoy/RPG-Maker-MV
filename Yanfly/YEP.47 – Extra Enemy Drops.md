##YEP.47 – Extra Enemy Drops
***
###Introduction
***
By default, RPG Maker MV limits enemies to only drop up to 3 items max and at very limited drop rates. This plugin allows you to add more than 3 items at drop. In addition to having more than 3 drops, this plugin also allows you to expand the enemy drops to have conditional drops, drops that will only appear before the player if certain conditions are met.

MV限制了敌方最多掉落3样物品以及严格的掉落概率。这个插件可以让你提高掉落数量，甚至可以设置条件掉落

***
###Generic Drop – Notetags
***

Use the following notetags to determine extra enemy drops. These drops will drop normally without any special conditions other than having to go through and pass a random number generator.

使用这些标签来决定额外掉落的物品。这个不会有条件掉落

####Enemy Notetags:

	<Item x: y%>
	<Weapon x: y%>
	<Armor x: y%>
Adds item, weapon, or armor ID of x to the enemy’s drop pool with a y% chance of dropping the item. Insert multiples of this notetag to add more drop items for the enemy drop pool.

设置掉落物品及概率

	<Enemy Drops>
	Item x: y%
	Weapon x: y%
	Armor x: y%
	</Enemy Drops>
Alternatively, using the above notetag format will allow you to group a large number of enemy drops together. Replace x with the item, weapon, or armor ID to give the item a drop rate of y%.

批量设置掉落物品及概率

	<Drop Potion: x%>
	<Drop Short Sword: x%>
	<Drop Feather Cap: x%>
If you prefer to use names instead, you can use the above format for the notetags. This will make the named item have a drop rate of x%. If you have multiple items in your database with the same name, priority will be given to the item with the highest ID in the order of item, weapons, then armors. Insert multiple multiples of this notetag to add more drop items for the enemy drop pool.

采用名字设置掉落物品及概率

	<Enemy Drops>
	Potion: x%
	Short Sword: x%
	Feather Cap: x%
	</Enemy Drops>
Alternatively, you can write your notetag like such to group together a list of named items. This will make the named item have a drop rate of x%. If you have multiple items in your database with the same name, priority will be given to the item with the highest ID in the order of item, weapons, then armors. Insert multiple multiples of this notetag to add more drop items for the enemy drop pool.

采用名字批量设置掉落物品及概率

***
###Conditional Drop – Notetags
***

Sometimes, you want certain conditions to be met before enemies will drop a specific item. These conditional drops would have a 0% chance otherwise. For each condition met, you can increase or decrease the drop rate. Use the below format to create a conditional drop.

如果你想设置特定条件掉落特定物品。你可以使用下面标签

####Enemy Notetags:

	<Conditional Item x Drop>
	condition: +y%
	condition: -y%
	<Conditional Item x Drop>

	<Conditional Weapon x Drop>
	condition: +y%
	condition: -y%
	<Conditional Weapon x Drop>

	<Conditional Armor x Drop>
	condition: +y%
	condition: -y%
	<Conditional Armor x Drop>
The above notetags will create the conditions for item, weapon, or armor x to drop. Insert various conditions in between the notetags to produce the conditional rate increases or decreases of y% for the drop.

设置特定条件下掉落物品及概率

	<Conditional Named Drop>
	condition: +y%
	condition: -y%
	<Conditional Named Drop>
If you prefer to name your drop, use the above format. If database entries have matching names, priority will be given to the item with the highest ID in the order of items, weapons, then armor. Insert various conditions in between the notetags to produce the conditional rate increases or decreases for y% for the drop.

采用名字设置特定条件下掉落物品及概率

The following are various conditions you may use:

####ALIVE MEMBERS EVAL

This checks the number of alive party members the player has when the drops are being calculated and made and runs it against an eval check.

存活队员

Example: 

	Alive Members > 1: +20%
	Alive Members === 2: +25%
	Alive Members <= 3: -30%

####ALWAYS

This condition will always pass. This can be used as setting a base rate for the item drop.

Example: 

	Always: +50%
	
	
####item x COUNT EVAL  
####weapon x COUNT EVAL  
####armor x COUNT EVAL  
####named item COUNT EVAL  

This checks the quantity of specific items, weapons, armors, and/or named items you have. If you choose a named item and multiple database entries share the name of that named item, priority will be given to the highest ID in the order of items, weapons, and then armor.

对比特定物品数量

Example: 

	Item 1 Count > 1: +20%
	Weapon 2 Count === 2: +25%
	Armor 3 Count <= 3: -30%
	Potion Count >= 4: +35%

####DEAD MEMBERS EVAL

This checks the number of dead party members the player has when the drops are being calculated and made and runs it against an eval check.

对比死亡人数

Example: 

	Dead Members > 1: +20%
	Dead Members === 2: +25%
	Dead Members <= 3: -30%

####DEATH TURN EVAL

This will run an eval check to compare the turn number the enemy has died. This plugin requires the Battle Engine Core.

死亡回合数

Example: 

	Death Turn > 5: +10%
	Death Turn === 5: +20%
	Death Turn <= 4: +30%

####EVAL code

This will run an eval check for the code you’ve inserted. If it returns true then the condition is met.

对比插入代码

Example: 

	Eval user.name() === ‘Bat A’: +30%

####LAST STRIKE SKILL X
####LAST STRIKE ITEM X
####LAST STRIKE named

This checks to see if the last strike on the enemy is item x, skill x, or a named action. If a named action is used and multiple database entries share the name of the action, priority will be given to the highest ID in the order of skills then items.

对比最后使用的物品或者技能

Example: 

	Last Strike Skill 40: +20%
	Last Strike Item 50: -30%
	Last Strike Firaga: +40%
	Last Strike Ice Bomb: -50%

####PARTY MEMBERS EVAL

This checks the number of party members (dead or alive) the player has when the drops are being calculated and made and runs it against an eval check.

对比队伍成员数量

Example: 

	Party Members > 1: +20%
	Party Members === 2: +25%
	Party Members <= 3: -30%

####RANDOM X%

This condition has a random x% chance to pass.

对比随机概率

Example: 

	Random 20%: +40%
	Random 30%: -60%

####TIMES ELEMENT X STRUCK EVAL

This compares the number of times the enemy has been struck by element x. You can also replace x with the name of the item.

对比敌方承受状态次数

Example: 

	Times Element Fire Struck > 6: +10%
	Times Element 3 Struck === 5: -10%
	Times Element Thunder <= 4: +20%

####TIMES ITEM X STRUCK EVAL

This compares the number of times the enemy has been struck by item x. You can also replace x with the name of the item.

对比敌方受物品攻击次数

Example: 

	Times Item Bomb Struck > 6: +10%
	Times Item 42 Struck === 5: -10%
	Times Item Uni Struck <= 4: +20%

####TIMES SKILL X STRUCK EVAL

This compares the number of times the enemy has been struck by skill x. You can also replace x with the name of the skill.

对比敌方受技能攻击次数

Example: 

	Times Skill Firaga Struck > 6: +10%
	Times Skill 40 Struck === 5: -10%
	Times Skill Thundaga Struck <= 4: +20%

####TIMES STATE X STRUCK EVAL

This compares the number of times the enemy has been struck by state x. You can also replace x with the name of the state.

对比敌方受状态次数

Example: 

	Times State 4 Struck > 6: +10%
	Times State Blind Struck === 5: -10%
	Times State Silence Struck <= 4: +20%

####TIMES STYPE X STRUCK EVAL

This compares the number of times the enemy has been struck by skill type x. You can also replace x with the name of the skill type.

对比敌方被技能类型攻击次数

Example: 

	Times SType 1 Struck > 6: +10%
	Times SType Magic Struck === 5: -10%
	Times SType Special Struck <= 4: +20%

####SWITCH X ON
####SWITCH X OFF

Replace X with a switch ID. If switch X is ON or OFF, the condition is met.

对比开关

Example: 

	Switch 5 ON: +10%
	Switch 6 OFF: -10%

####TURN EVAL

This will run an eval check to compare the number of turns the battle has gone on for until the time the drops have been made.

对比回合数

Example: 

	Turn > 5: +10%
	Turn === 5: +20%
	Turn <= 4: +30%

####VARIABLE X EVAL

Replace X with a variable ID. This will run an eval check to compare the variable’s value to see if it meets the conditions.

对比变量

Example: 

	Variable 5 > 10: +20%
	Variable 6 === 11: +25%
	Variable 7 <= 12: -30%

***
###Happy RPG Making!