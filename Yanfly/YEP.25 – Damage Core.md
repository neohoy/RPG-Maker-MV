##YEP.25 – Damage Core
***
###Introduction
***
The game gives a lot of control over the damage formula, but it doesn’t give much control for everything else after calculating the damage formula. This plugin will give you control over the order the damage fomrula is calculated in addition to letting you insert your own changes to the damage formula at whatever you you wish.

游戏中可以设置关于造成伤害的公式，但是并没有与计算伤害公式后的相关设置。利用这个插件，你可以插入你自己的调整进入伤害公式。

If you have YEP_BattleEngineCore.js installed, place this plugin under YEP_BattleEngineCore.js if you wish to make use of the extra features this plugin has to offer.

如果你使用了YEP_BattleEngineCore.js，把它放在YEP_BattleEngineCore.js下面

***
###Notetags
***

The following are some notetags you can use to modify the damage caps.

下面的标签你可以用来调整

####Skill and Item Notetag:

	<Bypass Damage Cap>
This causes the skill/item to ignore the damage cap and go with the regular value of the calculated damage. This will cancel out any damage cap effects otherwise. This will take priority over any damage cap breaking effects.

忽略伤害限制

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Bypass Damage Cap>
This will cause the related battler to bypass any damage capping effects and its skills/items will go with the uncapped calculated value.

忽略伤害限制

	<Damage Cap: x>
	<Heal Cap: x>
This will set the skill to have a damage/healing cap of x. This will cancel out any damage cap bypassers. If a battler has more than one damage cap, it will go with the highest value. This means if an actor that has a weapon that brings the damage cap to 99,999 and an accessory that brings the damage cap to 999,999, then the battler’s damage cap will be the highest value of 999,999.

设置伤害限制和治疗限制

***
###Plugin Commands
***

The following are plugins you can use to set the damage cap rulings for your game. Keep in mind that individual aspects such as equipment traits, skill properties, etc. will take priority over these default caps.

你可以用下面的插件命令来设置伤害限制规则。请注意，装备特性，技能特性将不会受影响

####Plugin Command:

	SetDamageCap 9999
Sets the default damage cap to 9999.

伤害上限为9999

	SetHealingCap 9999
Sets the default healing cap to 9999.

治疗上限为9999

	EnableDamageCap
Enables default cap for both damage and healing.

开启伤害上限

	DisableDamageCap
Disables default cap for both damage and healing.

关闭伤害上限

***
###Happy RPG Making!