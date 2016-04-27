##YEP.90 – Equip Battle Skills
***
###Introduction
***
This plugin creates a new gameplay mechanic where players have to choose which skills to bring into battle. They can select what skills to bring from the skill menu. In addition to being able to do that, equipped skills can also add bonuses such as stat stats and/or passive states.

这个插件一种全新的玩法，玩家可以选择带何种技能参与战斗，他们从技能菜单里面选择。为了能够实现这些，这些技能将会添加状态或者被动状态

Note: During Battle Test, equip skill slots will be disabled for the sake of better battle testing control.

注意：在战斗测试里面，装备技能入口将不能使用

***
###Notetags
***

The following notetags adjust various aspects about equippable battle skills.

你可以使用下面的标签

####Actor Notetag:
	<Starting Skill Slots: x>
This sets the actor’s starting skill slots to x amount. This value will not allow the actor to bypass the Maximum Skills limit.

技能选择数量

####Skill Notetags:
	<Equip stat: +x>
	<Equip stat: -x>
Replace ‘stat’ with ‘HP’, ‘MP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, or ‘LUK’ to have that stat increase or decrease by x amount while the skill is equipped for battle.

设置技能增加状态

	<Equip State: x>
	<Equip State: x, x, x>
	<Equip State: x through x>
This causes the actor to be affected by state x while the skill is equipped for battle.

设置技能使会携带的状态

	<Unequippable>
This skill cannot be equipped no matter what.

不能携带

	<All Access Equippable>
This makes the skill equippable whether the actor has the available skill type needed for the skill or not.

所有技能类型均可携带

	<Access Only Equippable>
This makes the skill equippable only for actors with the specific skill type. Actors without access to the skill type cannot equip it.

仅可携带开启的技能类型

####Class, Skill, Weapon, Armor, and State Notetags:
	<Equip Skill Slots: +x>
	<Equip Skill Slots: -x>
This increases or decreases the amount of skills the actor can equip for battle by x. This value will not allow the actor to bypass the Maximum Skills Limit.

增加或者减少技能携带数量

***
###Plugin Commands
***

You can use the following plugin commands to increase or decrease the amount of battle slots for specific actors.

插件命令

####Plugin Command:

	IncreaseActorBattleSlots 3 by 4
– This will increase actor 3’s number of battle skill slots by 4. The total amount of battle skill slots cannot go beyond the ‘Maximum Skills’ plugin parameter.

增加玩家3的技能数量为4

	DecreaseActorBattleSlots 5 by 2
– This will decrease actor 5’s number of battle skill slots by 2. The total amount of battle skill slots cannot go beneath 1.

增加玩家3的技能数量2，不可以低于1

***
###Happy RPG Making!