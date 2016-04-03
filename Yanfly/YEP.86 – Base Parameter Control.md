##YEP.86 – Base Parameter Control
***
###Introduction
***

The base parameters, MaxHP, MaxMP, ATK, DEF, MAT, MDF, AGI, and LUK all play a very important part of battle, yet, so very little control is given to the developer in regards to these important stats. This plugin will give more control over how the stats are handled and more.

基础参数，例如最大生命值，最大魔法值，攻击，防御，魔攻，魔防，速度，幸运等，发挥了非常重要的作用。然而缺乏必要的调整来开发他们。这个插件允许你更好地调节使用

Note: If you are using the Core Engine and have modified the settings there for higher parameter caps, this plugin will override those settings if this plugin is placed beneath the Core Engine (recommended).

注意：如果你使用了Core Engine，并且改变了参数设置，当你把插件放Core Engine下面时，在这个插件会覆盖原有设定
***
###Instructions – Base Parameter Explanation
***
For those who do not understand what the base parameters are used for in RPG Maker MV, this section will provide a brief summary of their most important roles of what the base parameters do.

下面是基础参数介绍，就是大家显而易见的一些数值
—

MHP – MaxHP
– This is the maximum health points value. The amount of health points (HP) a battler has determines whether or not the battler is in a living state or a dead state. If the HP value is above 0, then the battler is living. If it is 0 or below, the battler is in a dead state unless the battler has a way to counteract death (usually through immortality). When the battler takes damage, it is usually dealt to the HP value and reduces it. If the battler is healed, then the HP value is increased. The MaxHP value determines what’s the maximum amount the HP value can be held at, meaning the battler cannot be healed past that point.


—

MMP – MaxMP
– This is the maximum magic points value. Magic points (MP) are typically used for the cost of skills and spells in battle. If the battler has enough MP to fit the cost of the said skill, the battler is able to use the said skill provided that all of the skill’s other conditions are met. If not, the battler is then unable to use the skill. Upon using a skill that costs MP, the battler’s MP is reduced. However, the battler’s MP can be recovered and results in a gain of MP. The MaxMP value determines what is the maximum amount the MP value can be held at, meaning the battler cannot recover MP past the MaxMP value.

—

ATK – Attack
– This is the attack value of the battler. By default, this stat is used for the purpose of damage calculations only, and is typically used to represent the battler’s physical attack power. Given normal damage formulas, higher values mean higher damage output for physical attacks.

—

DEF – Defense
– This is the defense value of the battler. By default, this stat is used for the purpose of damage calculations only, and is typically used to represent the battler’s physical defense. Given normal damage formulas, higher values mean less damage received from physical attacks.

—

MAT – Magic Attack
– This is the magic attack value of the battler. By default, this stat is used for the purpose of damage calculations only, and is typically used to represent the battler’s magical attack power. Given normal damage formulas, higher values mean higher damage output for magical attacks.

—

MDF – Magic Defense
– This is the magic defense value of the battler. By default, this stat is used for the purpose of damage calculations only, and is typically used to represent the battler’s magical defense. Given normal damage formulas, higher values mean less damage received from magical attacks.

—

AGI – Agility
– This is the agility value of the battler. By default, this stat is used to determine battler’s position in the battle turn’s order. Given a normal turn calculation formula, the higher the value, the faster the battler is, and the more likely the battler will have its turn earlier in a turn.

—

LUK – Luck
– This is the luck value of the battler. By default, this stat is used to affect the success rate of states, buffs, and debuffs applied by the battler and received by the battler. If the user has a higher LUK value, the state, buff, or debuff is more likely to succeed. If the target has a higher LUK value, then the state, buff, or debuff is less likely to succeed.

—
***
###Instructions – Custom Formulas
***
The values calculated by the formulas in the plugin parameters are to come out as integer values. If the result is a float, it will be rounded up and then clamped based around the maximum and minimum values the parameter can be (also calculated by the plugin parameters).

下面是基础参数计算公式

By default, the formula looks as such:

—

	(base + plus)paramRatebuffRate + flat

—

Below is an explanation of each of the parts of the formula.

下面是对公式参数的介绍

BASE
– This value is determined in multiple ways. If the battler is an actor, the base value is the base parameter value calculated by the position based on the battler’s level on the parameter curve for the battler’s current class. If the battler is an enemy, the base parameter value, by default, is equal to the value inserted on the enemy’s database entry for that parameter.

基础值

PLUS
– This value is determined in multiple ways. For both actors and enemies, this value is a flat value given to the battler through events or script calls that manually increase the battler’s parameter value. If the battler is an actor, this value is also increased by any equipment the battler has equipped. This value can be influenced by notetags provided by this plugin.

增加值

PARAMRATE
– This value is determined the same way for both actors and enemies. This is a percentile rate that is calculated by the multiplicative product of all of the parameter spread across the battler’s traits, independent of the battler’s buff rate. This value can be influenced by notetags provided by this plugin.

参数调整率

BUFFRATE
– This value is determined by the number of buff stacks (or debuff stacks) on a battler, regardless of whether or not the battler is an actor or enemy. The percentile modifier is calculated relative to the number of stacks in regards to that particular parameter for the battler. This value is NOT influenced by notetags provided by this plugin.

状态效果调整

FLAT
– This is a new variable added by this plugin. Its purpose is to provide a final additive modifier to the total value of the parameter. This additive value is determined by the various database objects through notetags and can only be affected by those notetags.

定值
—

The parameter Maximum and Minimum values also have formulas. They will work something along the lines of this by default:

参数的上下限也有相应的公式

	customMax || (user.isActor() ? 9999 : 999999)
	customMin || 1

For those wondering about the ‘customMax’ and ‘customMin’ values, they are new variables added by this plugin.

下面是对公式参数的介绍

CUSTOMMAX
– This is the custom maximum limit provided by this plugin through either a script call or notetags. The custom max will look through the battler’s individual noteboxes. If the battler is an actor, it will look through the actor, class, each of the noteboxes of the equipment worn by the actor, and the noteboxes of each of the states affecting the actor. If the battler is an enemy, it wil look through the enemy notebox and each of the noteboxes of the states affecting the enemy. The highest custom maximum value becomes the
newest ‘customMax’ value for the battler and will take priority over the default maximum value. If there is no ‘customMax’ value, then the value becomes the default maximum value written in the formula.

自定义最大值

CUSTOMMIN
– This is the custom minimum limit provided by this plugin through either a script call or notetags. The custom min will look through the battler’s individual noteboxes. If the battler is an actor, it will look through the actor, class, each of the noteboxes of the equipment worn by the actor, and the noteboxes of each of the states affecting the actor. If the battler is an enemy, it wil look through the enemy notebox and each of the noteboxes of the states affecting the enemy. The highest custom minimum value becomes the newest ‘customMin’ value for the battler and will take priority over the default minimum value. If there is no ‘customMin’ value, then the value becomes the default minimum value written in the formula.

自定义最小值


***
###Notetags
***
You can use the following notetags to alter the various aspects that modify the base parameter values:

你可以使用下面标签来设定

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<stat Plus: +x>
	<stat Plus: -x>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. This is the value added to the base parameter before the rate and flat values contribute to the total parameter value assuming the plugin’s default formula is utilized.

更改参数公式的增加值

	<stat Rate: x%>
	<stat Rate: x.y>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. This is the value multiplied to the sum of the base and plus of the parameter before affected by the buffRate and flat value assuming the plugin’s default formula is utilized.

更改参数公式的参数调整率

	<stat Flat: +x>
	<stat Flat: -x>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. This is the value added at the end after the sum of the base and plus parameters have been added and multiplied by the rate values assuming the plugin’s default formula is utilized.

更改参数公式的定值

	<stat Max: x>
	<stat Min: x>
Replace ‘stat’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. This sets the maximum or minimum cap of the the stat parameter to x. If a battler is affected by multiple of these notetags, then the value used will be the largest value of the notetag used.

更改参数公式上下限

***
###Happy RPG Making!



