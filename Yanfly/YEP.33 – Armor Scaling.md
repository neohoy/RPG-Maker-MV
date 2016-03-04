##YEP.33 – Armor Scaling

Scale defensive stats relative to a universal scale and gives your players a way to increase and decrease damage without having to provide pure stats. Adds new gameplay mechanics such as Armor Penetration and Armor Reduction into your game!

分级是一个很大的范围，并且可以给玩家提供更多或者更少的伤害。可以制作装备穿透力或者减伤效果

This plugin requires Damage Core.

这个插件需要Damage Core

***
###Introduction
***

This plugin requires YEP_DamageCore. Make sure this plugin is located under YEP_DamageCore in the plugin list.

这个插件需要YEP_DamageCore，确保插件在YEP_DamageCore下面

This plugin serves as a damage balancing plugin to make numbers across the battlefield more universal for both actors and enemies alike and gets past the flaws that ATK – DEF formulas have.

这个插件用来调整伤害

***
###Armor Scaling
***

Armor Scaling allows the damage formula to be rid of “b.def * 2” and similar calculations in favor of scaling the damage relative to the armor values that the attack target has. The following is the armor scaling formula for both positive and negative armor values:

装备分级允许伤害公式摆脱内置公式，并且帮助为装备伤害值进行分级。下面是装备分级公式

Positive Armor 

	Rate = 100 / (100 + Armor)

Negative Armor

	Rate = 2 – (100 / [100 – Armor])

To get an idea of how armor scaling will affect damage, here’s a table on how 1,000 base damage is affected.

为了理解装备分级是如何影响伤害的，这里有一个基于100伤害的列表作为例子

Using the default base armor formula of 2 defense points is equal to 1 armor, this means at 200 defense, a battler will take only 50% damage. At 999 defense, the battler will take a little bit more than 16.67% damage. At those values without armor scaling, damage can be entirely undone for that very matter. This goes to show how effective armor scaling can be to maintain long-term balancing.

使用默认的装备公式，2点防御等于1点护甲。这意味着200防御，敌方尽可以造成一半伤害。在999防御的时候，战斗者将会造成接近16.67%的伤害。如果没有装备分级，伤害就会这样造成，现在我们看一下分级后的效果

***
###Armor Reduction and Armor Penetration
***

There are various modifiers that can alter the armor level before the armor scaling rate is applied to damage. Armor goes through four main steps and they are as follows.

这里有很多装备等级的可调整项。装备将会按照下面四步进行计算

1. Armor Reduction, Flat
2. Armor Reduction, Percentage
3. Armor Penetration, Percentage
4. Armor Penetration, Flat

In step 1 (Armor Reduction, Flat), the target’s armor is reduced by a value. Flat armor reduction stacks additively. Flat armor reduction can reduce a target’s armor below zero. For example, if an enemy with 10 armor has their armor reduced by 25, the enemy will have -15 armor. Armor reduction values are provided by target and not the attacker.

护甲减少定值

In step 2 (Armor Reduction, Percentage), the target’s armor is multiplied by a percentage (100% – the listed value). Percentage armor reduction stacks multiplicatively and is ignored if the target’s armor is 0 or less. Percentage armor reduction makes a bigger difference on targets with higher armor. For instance, with 40% armor reduction, a target with 200 armor will lose 80 while a target with only 50 armor will lose 20. Armor reduction values are provided by the target and not the attacker.

护甲减少百分比

In step 3 (Armor Penetration, Percentage), the target’s armor is multiplied by a percentage (100% – the listed value). Percentage armor penetration stacks multiplicatively and is ignored if the target’s armor is 0 or less. Percentage armor penetration makes a bigger difference on targets with higher armor. For instance, with 40% armor penetration, a target with 200 armor will be considered as having 80 less while a target with only 50 armor will be considered as having 20 less. Armor penetration values are provided by the attacker and not the target.

护甲穿透百分比

In step 4 (Armor Penetration, Flat), the target’s armor is treated as being reduced by an amount for purposes of damage calculation, but cannot be reduced below 0. Flat armor penetration stacks additively. Armor penetration values are provided by the attacker and not the target.

护甲穿透定值

***
###Notetags
***

You may use these notetags to adjust various factors for armor scaling rates and calculations.

你可以使用下面标签来调整装备升级概率

Skill and Item Notetags:

	<Armor Reduction: x>
Causes the skill/item to reduce the target’s armor level by x. This is calculated first above everything else.

按定值减少护甲等级

	<Armor Reduction: x%>
Causes the skill/item to reduce the target’s armor level by x%. This is calculated second but is ignored if the armor level is less than 0.

按百分比减少护甲等级

	<Armor Penetration: x%>
Causes the skill/item to reduce the target’s armor level by x% (but will not go past 0). This is calculated third.

按百分比进行护甲穿透


	<Armor Penetration: x>
Causes the skill/item to reduce the target’s armor level by x (but will not go past 0). This is calculated last.

按定值进行护甲穿透

	<Bypass Armor Scaling>
This notetag allows you to bypass the armor scaling process for this individual skill/item.

忽略装备分级

####Actor, Class, Enemy, Weapon, Armor, State Notetags:

	<Physical Armor Reduction: x>
Causes this actor to lose x armor when targeted by physical skills/items. This is calculated first.

物理护甲减少

	<Magical Armor Reduction: x>
Causes this actor to lose x armor when targeted by magical skills/items. This is calculated first.

魔法护甲减少

	<Certain Armor Reduction: x>
Causes this actor to lose x armor when targeted by certain skills/items. This is calculated first.

真实护甲减少

	<Physical Armor Reduction: x%>
Causes this actor to lose x% armor when targeted by physical skills/items. This is calculated second.

物理护甲减少百分比

	<Magical Armor Reduction: x%>
Causes this actor to lose x% armor when targeted by magical skills/items. This is calculated second.

魔法护甲减少百分比

	<Certain Armor Reduction: x%>
Causes this actor to lose x% armor when targeted by certain skills/items. This is calculated second.

真实护甲减少百分比

	<Physical Armor Penetration: x%>
Causes this actor to cause the target to lose x% armor when using a physical skills/items. This is calculated third.

物理护甲穿透百分比

	<Magical Armor Penetration: x%>
Causes this actor to cause the target to lose x% armor when using a magical skills/items. This is calculated third.

魔法护甲穿透百分比

	<Certain Armor Penetration: x%>
Causes this actor to cause the target to lose x% armor when using a physical skills/items. This is calculated third.

真实护甲穿透百分比

	<Physical Armor Penetration: x>
Causes this actor to cause the target to lose x armor but not drop below 0 armor when using a physical skills/items. This is calculated last.

物理护甲穿透

	<Magical Armor Penetration: x>
Causes this actor to cause the target to lose x armor but not drop below 0 armor when using a magical skills/items. This is calculated last.

魔法护甲穿透

	<Certain Armor Penetration: x>
Causes this actor to cause the target to lose x armor but not drop below 0 armor when using a certain skills/items. This is calculated last.

真实护甲穿透

***
###Happy RPG Making!