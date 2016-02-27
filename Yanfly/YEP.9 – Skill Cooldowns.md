##YEP.9 – Skill Cooldowns

Skill Cooldowns is an extension plugin for the Skill Core. This plugin enables you to give your skills cooldowns, a game mechanic which prevents skills from being repeatedly used requiring the player to wait a few turns in order for the skill to become available for use again.

技能冷却是一个技能核心的拓展插件。这个插件可以让你实现技能冷却，让玩家需要等待几个回合才能继续使用。

***
###Introduction
***

This plugin requires YEP_SkillCore.
Make sure this plugin is located under YEP_SkillCore in the plugin list.

这个插件需要YEP_SkillCore，确保它放在YEP_SkillCore下面

This plugin allows you to give your skills cooldowns. Cooldowns are a limit enforced on a skill to prevent them from being used constantly.

这个插件让你实现技能冷却，避免连续使用技能

***
###Cooldown Types
***

####Cooldown (Standard)
The standard cooldown only occurs if the skill has a cooldown to pay. When used, the skill cannot be used for x turns as indicated by the cooldown. There are a number of things that contribute to cooldowns going down. The first would be simply waiting. Each turn in battle causes a cooldown to drop by 1 turn. Skills and the such can be used to speed up this process. The second would be to finish battles. Finishing a battle will cause all cooldowns to drop by a certain amount (can be defined in the parameters). And the third would be walking on the field map. Every certain amount of steps allow a skill’s cooldown to decrease.

标准冷却。当被使用时，技能需要等x回合才可以使用。这里可以利用某些东西让冷却降低。最简单的就是等待，每回合都会降低。技能或者类似的也可以降低冷却。除此之外，你还可以结束战斗，战斗结束后冷却都会到一个定值。第三种方法就是在地图上走动，走动步数可以降低冷却

####Warmups
As far as most things go, Warmups do the same thing as Cooldowns: prevent skills from being used until their timer is up. The difference, however, is that warmups only occur once during battle: at the very start of it. If a skill has a warmup timer, it will trigger the moment it goes into battle and instantly disappear after battle. Warmups do not stack on top of any existing cooldowns. If a cooldown is already occurring when a skill is in the warmup phase, both the warmup and cooldown simultaneously update.

就大多数而言，热身和冷却一样，时间结束才可以使用技能，区别是，热身仅仅发生在战斗一开始。如果一个技能有热身时间，他会进入战斗中触发，战斗结束后小时。热身不会叠在任何冷却之上，当技能同时拥有冷却和热身时，会同步更新

####Linked Cooldowns
A linked cooldown occurs when a skill that’s used causes another skill in the owner’s skill library to have a cooldown. All other attributes of this cooldown are the same as a standard cooldown’s. This cooldown type will take priority over Skill Type Cooldowns and Global Cooldowns if this value is defined.

关联冷却是某个技能造成另一个技能冷却时。所有的冷却都看做关联冷却。冷却将会优先考虑技能冷却和全局冷却

###Skill Type Cooldowns
When a Skill Type Cooldown occurs, all skills currently in the battler’s skill library with the matching Skill Type will be on cooldown. All other attributes of this cooldown are the same as a standard cooldown’s. This cooldown type will take priority over Global Cooldowns if this value is defined.

当技能类型冷却时，所有匹配的技能类型都在冷却中。另外的技能将会是标准冷却。技能冷却优先考虑全局冷却

When a cooldown is applied for a skill that already has a cooldown, the cooldown will change to whatever is the largest value. This means if a skill has 3 turns for a cooldown and a Skill Type Cooldown would set for 1 turn, the 3 turns would remain. On the flip side, if the skill has 3 turns and the Skill Type Cooldown would set for 5 turns, then the cooldown would be changed to 5 turns instead.

当冷却应用于已存在冷却的技能，冷却将会改变最大值。这意味着，当一个技能有3回合冷却时，技能类型冷却设置为1回合，则3回合会保留。如果技能有3回合冷却，技能类型冷却设置为5回合，冷却时间变更为5回合

***
###Notetags
***

Use the following notetags to alter the cooldown properties of a skill.

使用下面的标签来改变冷却

####Skill Notetags:
	<Cooldown: x>
Sets the cooldown for the skill to X turns. This cooldown only affects this skill alone. This value will take priority over Skill Type Cooldowns and Global Cooldowns.

设计技能冷却回合数x。这只会影响技能自身。这个值会优先考虑技能类型冷却和全局冷却

	<After Battle Cooldown: +x>
	<After Battle Cooldown: -x>
After a battle ends (victory, loss, or escape), change the cooldown for this skill by +x turns or -x turns.

战斗之后，技能冷却增加或者减少

	<Cooldown Steps: x>
Outside of battle, every x steps that the Player takes, this skill’s cooldown will drop by 1.

每走x步，技能冷却减少1

	<Skill x Cooldown: y>
When using this skill, after paying the skill cost, skill x will have a linked cooldown of y turns. This value will take priority over Skill Type Cooldowns and Global Cooldowns.

使用技能后，并且支付技能消耗以后，技能x将会关联冷却y回合。这个值优先考虑技能类型冷却和全局冷却

	<SType x Cooldown: y>
When using this skill, after paying the skill cost, all skills with the matching Skill Type x to have a cooldown of y. This value will take priority over Global Cooldowns.

使用技能后，并且支付技能消耗以后，所有技能类型x将会关联冷却y回合。这个值优先考虑全局冷却

	<Global Cooldown: x>
When using this skill, all skills within the battler’s skill library area set to be on cooldown for x turns. This value has less priority than Individual Cooldowns and Skill Type Cooldowns.

使用技能后，所有技能将会设置冷却x回合。这个值优先于独立冷却和技能类型冷却

	<Bypass Cooldown>
This causes the skill to bypass cooldowns, no matter what. This should be used for skills like Attack, Guard, Escape, etc. that should not have a cooldown assigned to them.

技能不需要冷却。例如攻击，防御，逃跑等不需要冷却的指令。

####Skill and Item Notetags:
	<Skill x Cooldown: +y>
	<Skill x Cooldown: -y>
Targets hit by this skill will have skill x’s cooldown adjusted by y. This does not apply to the user and applies only to the targets.

目标技能x的冷却增加或者减少。仅适用于目标，不能用于自己

	<SType x Cooldown: +y>
	<SType x Cooldown: -y>
Targets hit by this skill will have all skills in their skill library with Skill Type x to have their cooldowns adjusted by y. This does not apply to the user and applies only to the targets.

目标技能类型x的冷却增加或者减少。仅适用于目标，不能用于自己

	<Global Cooldown: +x>
	<Global Cooldown: -x>
Targets hit by this skill will have all skills in their skill library to have their cooldowns adjusted by y. This does not apply to the user and applies only to the targets.

目标全部技能的冷却增加或者减少x。仅适用于目标，不能用于自己

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:
	<Skill x Cooldown Duration: y%>
Alters the cooldown duration of skill x to y% when the cooldown cost is applied. This effect only applies to skill x.

改变技能x的冷却持续时间为y%。

	<SType x Cooldown Duration: y%>
Alters the cooldown duration of skills with Skill Type x to y% when the cooldown cost is applied. This effect only applies to Skill Type x.

改变技能类型x的冷却持续时间为y%。

	<Global Cooldown Duration: x%>
Alters the cooldown duration of all skills to x% when the cooldown cost is applied.

改变全部技能的冷却持续时间为x%。

	<Skill x Cooldown Rate: y%>
Sets the cooldown rate for skill x to y% when the cooldown counter goes down. This effect only applies to skill x.

冷却需要下降时，技能x的冷却率为y%。

	<SType x Cooldown Rate: y%>
Sets the cooldown rate for Skill Type x skills to y% when the cooldown counter goes down. This effect only applies to Skill Type x skills.

冷却需要下降时，技能类型x的冷却率为y%。

	<Global Cooldown Rate: x%>
Sets the cooldown rate for all skills to x% when the cooldown counter goes down.

冷却需要下降时，全部技能的冷却率为x%。

	<Skill x Cooldown: +y>
	<Skill x Cooldown: -y>
If the user performs skill x, it will have an increased or decreased cooldown value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat cooldown modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，这个技能x冷却将会改变y。这将在所有计算完成后应用一个平均冷却。

	<SType x Cooldown: +y>
	<SType x Cooldown: -y>
If the user performs skill with skill type x, it will have an increased or decreased cooldown value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat cooldown modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，这个技能类型x冷却将会改变y。这将在所有计算完成后应用一个平均冷却。

	<Global Cooldown: +x>
	<Global Cooldown: -x>
If the user performs any skill, it will have an increased or decreased cooldown value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat cooldown modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，全部技能冷却将会改变x。这将在所有计算完成后应用一个平均冷却。

	<Skill x Warmup: +y>
	<Skill x Warmup: -y>
At the start of battle, skill x will have an increased or decreased warmup value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat warmup modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，战斗开始时，技能x热身时间改变y。这将在所有计算完成后应用一个平均热身时间。

	<SType x Warmup: +y>
	<SType x Warmup: -y>
At the start of battle, all skills with skill type x it will have an increased or decreased warmup value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat warmup modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，战斗开始时，技能类型x热身时间改变y。这将在所有计算完成后应用一个平均热身时间。

<Global Warmup: +x>
<Global Warmup: -x>
At the start of battle, all skills will have an increased or decreased warmup value as long as the user is the actor, class, enemy, or has the weapon or armor equipped, or is affected by the state with this notetag. These flat warmup modifications are applied after the rates and duration modifiers have been calculated.

如果玩家是特点玩家，职业，或者装备特定物品时，或者存在特点状态，战斗开始时，全部技能热身时间改变x。这将在所有计算完成后应用一个平均热身时间。

***
###Happy RPG Making!