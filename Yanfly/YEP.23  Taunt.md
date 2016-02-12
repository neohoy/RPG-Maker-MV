## YEP.23 – Taunt

Taunts have become a mainstream game mechanic for many games. It’s only natural to port something like that over to RPG Maker MV! Included in this plugin are taunt effects and taunt nullification effects!

嘲讽已经成为许多游戏的主流设定。但是对于RPG Maker MV确实没有改良的。通过这个插件，你可以改变嘲讽的影响

***
### Introduction
***

Taunts add a new mechanic to battle. Whenever a unit has a member with a taunt trait, the opposing unit’s single target attacks and skills must focus on the taunting unit. This adds aggro control for either unit and can add a new level of depth for battle. Taunts are divided up into physical, magical, and certain hit taunts which respectively aggro physical actions, magical actions, and certain hit actions.

嘲讽为战斗添加了新的技术。当一个单位拥有嘲讽效果，对方必须强制选择此作为攻击和技能的对象。这导致增加了对其他单元的控制麻烦，并且增加了战斗的深度。嘲讽被分成物理，魔法和真实打击。

If there are multiple users with taunt, the rival party can select which taunt user to attack. This is to prevent a lockdown caused by a rival unit making the battle impossible to progress.

如果这里多个嘲讽角色，则可以选择任意一个。这就防止了战斗进程的卡死。

***
### Notetags
***

The following are some notetags you can use to add taunt traits to your various database objects.

下面是一些你可以添加进入你的数据库的嘲讽特点。

####Actor, Class, Weapon, Armor, State, Enemy Notetags:

	<Physical Taunt>
	<Magical Taunt>
	<Certain Taunt>
	
These three notetags enable the database object of choice to have the respective taunt mechanic against those types of actions. Physical taunts will cause the user to aggro all physical type of actions from the rival team. The same goes for magical taunts and certain taunts of their nature.

这标签可以设置接受嘲讽的攻击

	<Null Physical Taunt>
	<Null Magical Taunt>
	<Null Certain Taunt>
	
This nullifies the respective taunt trait on the user (not the attacker). What this means is if a user originally has taunt through some form or means, having a null taunt trait applied will remove that taunt effect and the user will be treated as a normal target.

这标签可以设置不接受嘲讽的攻击

	<Ignore Physical Taunt>
	<Ignore Magical Taunt>
	<Ignore Certain Taunt>
	
This allows an attacker with this trait to ignore any taunts of the respective nature and gain access to all possible targets as if no taunts are in place.

这标签可以设置忽略嘲讽的攻击

#### Skill and Item Notetag:
	<Bypass Taunt>
	
This causes this skill/item to ignore taunts altogether and the skill/item is able to select single targets as if no taunts existed on the field.

这可以让技能或者物品忽略嘲讽

***
### Happy RPG Making!