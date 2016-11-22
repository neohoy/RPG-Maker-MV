##YEP.117 – Passive Aura Effects – RPG Maker MV

###Introduction

This plugin requires YEP_AutoPassiveStates. Make sure this plugin is located under YEP_AutoPassiveStates in the plugin list.

这个插件需要YEP_AutoPassiveStates。确保这个插件在YEP_AutoPassiveStates下面。

Passive Aura Effects are commonly found in many online multiplayer games with RPG elements. When a battler can give out an aura, it will affect other nearby battlers, too, either ally and/or foe. This plugin will allow states to generate aura effects for other party members, opponents, or specifically for actor and/or enemy parties.

被动群体效果经常在许多大型在线游戏中出现。当一个战斗者发动效果，周围的战斗者也会受到影响，包括队友或者敌群。这个插件可以让状态产生群体效果。

###Notetags

Use the following notetags to make a state generate auras.

使用下面的备注来制作群体状态

####State Notetags:

	<Ally Aura: x>
	<Ally Aura: x, x, x>
	<Ally Aura: x through y>
– This will cause the battler’s allies to gain state(s) x (through y) while the battler is affected by the current state.
*Note: A state cannot use itself in an aura effect.

当战斗者处于某状态时，这会让队友获得状态x

	<Foe Aura: x>
	<Foe Aura: x, x, x>
	<Foe Aura: x through y>
– This will cause the battler’s foes to gain state(s) x (through y) while the battler is affected by the current state.
*Note: A state cannot use itself in an aura effect.

当战斗者处于某状态时，这会让敌群获得状态x

	<Party Aura: x>
	<Party Aura: x, x, x>
	<Party Aura: x through y>
– This will cause the Actor Party to gain state(s) x (through y) while the battler is affected by the current state.
*Note: A state cannot use itself in an aura effect.

当战斗者处于某状态时，这会让队伍获得状态x(此处暂时无法却别ally和party的区别）

	<Troop Aura: x>
	<Troop Aura: x, x, x>
	<Troop Aura: x through y>
– This will cause the Enemy Troop to gain state(s) x (through y) while the battler is affected by the current state.
*Note: A state cannot use itself in an aura effect.

当战斗者处于某状态时，这会让敌群获得状态x(此处暂时无法却别foe和troop的区别）

###Lunatic Mode – Custom Aura Conditions

For those with JavaScript experience and would like to make conditional aura effects, you can use these notetags. Keep in mind, this conditional effect is for the target delivered state and not the origin aura itself.

下面是自定义模式

####State Notetags:

	<Custom Aura Condition>
	if (user.hpRate() > 0.50) {
	condition = true;
	} else {
	condition = false;
	}
	</Custom Aura Condition>
– The ‘condition’ variable will determine whether or not the target aura state will appear. If the ‘condition’ variable is ‘true’, then it will appear. If the ‘condition’ variable is ‘false’, then it will not appear. Remember, this notetag has to be placed in the target delivered state and not the origin aura itself.

condition用来决定这个状态是否出现，请记住，这个备注需要放在目标状态上，而不是初始状态上

###Happy RPG Making!