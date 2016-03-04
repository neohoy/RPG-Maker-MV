##YEP.26 – Critical Control
***
###Introduction
***

This plugin requires YEP_DamageCore.
Make sure this plugin is located under YEP_DamageCore in the plugin list.

这个插件需要YEP_DamageCore，确保放在YEP_DamageCore下面

This plugin allows you to modify the critical hit rate formula across a global scale and for an individual skill/item scale.

这个插件可以让你调整暴击率

***
###Notetags
***

You may use these notetags to adjust various factors for critical success rates and critical damage adjustments.

你可以用这些标签来调整暴击率和暴击值

####Skill and Item Notetags:

	<Critical Rate: x%>
This sets the skill/item’s critical hit rate to x%, ignoring any critical hit rate bonuses the user may have an ignoring any critical hit evasion bonuses the target may have.
*Note: Using this tag sets the skill/item to enable Critical Hits.

设置暴击率

	<Critical Rate: x.y>
This sets the skill/item’s critical hit rate to the float x.y, ignoring any critical hit rate bonuses the user may have an ignoring any critical hit evasion bonuses the target may have.
*Note: Using this tag sets the skill/item to enable Critical Hits.

设置暴击率

	<Critical Multiplier: x%>
This sets the skill/item’s critical damage multiplier as x% while still factoring in the user’s critical damage multiplier bonuses.
*Note: Using this tag sets the skill/item to enable Critical Hits.

设置暴击伤害比率

	<Critical Multiplier: x.y>
This sets the skill/item’s critical damage multiplier as x.y while still factoring in the user’s critical damage multiplier bonuses.
*Note: Using this tag sets the skill/item to enable Critical Hits.

设置暴击伤害比率

	<Flat Critical: x% stat>
Increases the skill/item’s flat critical bonus by x% of ‘stat’. Replace ‘stat’ with ‘hp’, ‘mp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. Using multiple instances of this notetag will override the previous.

暴击对状态的影响

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Critical Multiplier: +x%>
	<Critical Multiplier: -x%>
Alters the damage of a critical hit by x% for this actor, class, enemy, weapon, armor, or state. This is an additive trait.

设置暴击比率

	<Flat Critical: +x>
	<Flat Critical: -x>
Alters the damage of a critical hit by +x or -x for this actor, class, enemy, weapon, armor, or state. This is an additive trait.

暴击值

	<Certain Hit Critical Rate: +x%>
	<Certain Hit Critical Rate: -x%>
Alters the critical hit critical rate chance of certain hit skills for the user by +x% or -x% if this notetag exists in the actor, class, enemy, weapon, armor, or state notetags. This is an additive trait.

真实伤害暴击率

	<Physical Critical Rate: +x%>
	<Physical Critical Rate: -x%>
Alters the physical critical rate chance of certain hit skills for the user by +x% or -x% if this notetag exists in the actor, class, enemy, weapon, armor, or state notetags. This is an additive trait.

物理暴击率

	<Magical Critical Rate: +x%>
	<Magical Critical Rate: -x%>
Alters the magical critical rate chance of certain hit skills for the user by +x% or -x% if this notetag exists in the actor, class, enemy, weapon, armor, or state notetags. This is an additive trait.

魔法暴击率

***
###Happy RPG Making!