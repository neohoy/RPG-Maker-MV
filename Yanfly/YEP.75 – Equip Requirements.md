##YEP.75 – Equip Requirements
***
###Introduction
***
This plugin requires YEP_EquipCore.js to work. Place this plugin beneath YEP_EquipCore.js in the Plugin Manager list.

这个插件需要YEP_EquipCore.js，请把它放在YEP_EquipCore.js下面

Place restrictions on when an actor can equip a weapon or piece of armor. Set level requirements, stat requirements, switch requirements, and more. This plugin will also provide a separate equipment requirement window to show the player what is needed in order for gear to be equipped.

设置装备限制，例如等级限制，状态限制。这个插件可以提供单独的装备限制窗口给玩家，告诉他们需要什么

***
###Notetags
***

You can use these notetags to implement requirements onto your weapons and armors. These notetags will have to be set up in a certain way:

你可以使用标签来设置限制。

####Weapon and Armor Notetags:

	<Equip Requirement>
	requirement
	requirement
	</Equip Requirement>
– The main requirements will have to be placed in between these notetags. You can have a multitude of requirements for your weapons/armors. Replace ‘requirement’ with any of the following below:

主要需要放在这些标签里面。你可以设置多个需求

Weapon and Armor Requiprements:

	param > x
	param >= x
	param === x
	param <= x
	param < x
– Replace ‘param’ with ‘level’, ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. This will make the piece of equipment require the actor’s base parameter to be greater than (>), greater than or equal to (>=), equal to (===), less than or equal to (<=), or less than (<). This is NOT the value for the total parameter, only the base parameter.

设置等级，状态等等限制。这些数值指的是基础数值而不是最后叠加数值

	class: x
	class: name
– This will make the piece of equipment require the actor to be class x. If ‘name’ is used, priority will be given to the class with the highest ID in the database. Insert multiple of these requirements to add more classes. Having multiple classes will mean that the actor can be any of those classes to be able to equip the gear.

设置需要职业

	skill: x
	skill: name
– This will make the piece of equipment require the actor to have learned skill x. If ‘name’ is used, priority will be given to the skill with the highest ID in the database. Insert multiple of these requirements to add more skills. Having multiple skills means the actor must have learned ALL of the skills to be able to equip the gear.

设置需求技能

NOTE: The actor needs to have LEARNED the skill. This means that if you have added a skill to the actor’s skill library through a trait, it will not count.

玩家必须通过学习习得这个技能。如果通过特性赋予，则不会生效

	switch: x
– This will require switch X to be on. If it isn’t, the piece of equipment cannot be worn. Insert multiple of these to add more switches that are are required to be on.

需要开关x打开

***
###Happy RPG Making!