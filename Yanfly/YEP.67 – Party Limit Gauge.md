##YEP.67 – Party Limit Gauge

***
###Introduction
***

This plugin requires YEP_SkillCore. Make sure this plugin is located under YEP_SkillCore in the plugin list.

这个插件需要YEP_SkillCore。确保它放在YEP_SkillCore下面

This plugin enables a Party Limit Gauge for both the player party and the enemy party. These gauges will fill up or decrease depending on what actions take place. The amounts they raise can be adjusted within the plugin’s parameters to your liking. Once a party has enough of the Party Limit Gauge, members from that party can use it as a skill resource to unleash powerful actions in battle!

这个插件开启了队伍限制槽，适用于玩家和敌方。这些槽将会根据行动增加和减少。你可以用插件参数更改增长数值。只要队伍充满槽，队伍成员就可以使用更加强大的战斗行动

***
###Instructions – Limit Gain
***

There are various ways for the Party Limit Gauge to raise. The settings are adjusted in the plugin parameters but here will be a detailed explanation of what each parameter does:

这里有很多增加队伍限制槽的方式，你可以用插件参数调整，这里有一个详细的参数说明

Reset Gauge
– If set to true, then the Party Limit Gauge will empty out at the start of each battle. If set to false, the Party Limit Gauge will carry to each battle for the player party. The enemy party will always empty out.

如果设置为true,队伍限制槽将会在战斗后重置为空。如果是false，队伍限制槽将会保留。敌方限制槽将总是为空。

Battle Start
– This determines how much of the Party Limit Gauge will be gained when a new battle has been started.

开始战斗时增加数值

Take HP Damage
– This is how much the Party Limit Gauge will increase when an ally takes HP damage dealt by the opposing team.

遭受伤害时增加数值

Deal HP Damage
– This is how much the Party Limit Gauge will increase when an ally deals HP damage to the opposing team.

造成伤害时增加数值

Heal HP Damage
– This is how much the Party Limit Gauge will increase whenever an ally receives HP healing through actions. Healing done through trait effects will not apply here.

治疗血量时增加数值。通过特性影响治疗不在此范围

Take MP Damage
– This is how much the Party Limit Gauge will increase when an ally takes MP damage dealt by the opposing team.

遭受魔法损失时增加数值

Deal MP Damage
– This is how much the Party Limit Gauge will increase when an ally deals MP damage to the opposing team.

造成魔法损失时增加数值

Heal MP Damage
– This is how much the Party Limit Gauge will increase whenever an ally receives MP healing through actions. Healing done through trait effects will not apply here.

治疗魔法时增加数值。通过特性影响治疗不在此范围

Gain State
– This is how much the Party Limit Gauge will increase whenever an ally receives a non-death state from the opposing team.

获得状态时增加数值

Deal State
– This is how much the Party Limit Gauge will increase whenever an ally inflicts a non-death state to the opposing team.

给对方施加状态增加数值

Killed Ally
– This is how much the Party Limit Gauge will increase whenever an ally dies in battle.

友军死亡增加数值

Killed Foe
– This is how much the Party Limit Gauge will increase whenever a foe dies in battle.

敌军死亡增加数值

Win Battle
– This is how much the Party Limit Gauge will increase for the player’s party when the player wins a battle.

战斗胜利增加数值

Flee Battle
– This is how much the Party Limit Gauge will increase for the player’s party when the player escapes a battle.

战斗逃跑增加数值

Lose Battle
– This is how much the Party Limit Gauge will increase for the player’s party when the player loses a battle.

战斗失败增加数值

***
###Notetags
***

You can use these notetags to adjust the Party Limit Gauge aspects.

你可以使用下面的标签来调整

####Skill Notetags:

	<Party Limit Cost: x>
Adds a Party Limit Gauge cost to this skill. This skill will require x increments of the Party Limit Gauge to be able to use it.

消耗队伍限制槽数值

	<Party Limit Cost: x%>
Adds a party Limit Gauge cost to this skill equal to x% of the total max gauge size of the battler’s party max limit gauge size. The cost is always rounded upward.

消耗队伍限制槽数值百分比，这个数值是向上取值

####Skill and Item Notetags:

	<Ally Party Limit Gauge: +x>
	<Ally Party Limit Gauge: -x>
Using this skill will cause the user’s party limit gauge to increase or decrease by x. This is the point value cost and not the increment value.

使用技能队伍限制槽增加或减少x

<Foe Party Limit Gauge: +x>
<Foe Party Limit Gauge: -x>
Using this skill will cause the foe’s party limit gauge to increase or decrease by x. This is the point value cost and not the increment value.

使用技能敌军限制槽增加或减少x

####Actor and Enemy Notetag:

	<Party Limit: x>
Increases the Party Limit Gauge by x when this party member is present in battle (dead or alive). If this notetag isn’t used, the value will default to the settings in the plugin parameters.

当角色在战斗队伍时，增加队伍限制槽x，如果没有使用这个标签，则采用插件默认设置

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Party Limit: +x>
	<Party Limit: -x>
Increases or decreases the Party Limit Gauge by x if the related unit has is that actor, class, enemy, or has the weapon or armor equipped, or is affected by that state.

如果角色装备有特点武器，装备或者处于特点状态，则增加或者减少队伍限制槽

	<Party Limit Cost: x%>
Sets the party limit costs paid by this actor to x%. The modifications are are multiplicative. The final cost is always rounded upward.

队伍限制槽通过这个角色花费x%

***
###Happy RPG Making!

