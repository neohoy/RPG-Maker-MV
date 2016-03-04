##YEP.70 – Absorption Barrier
***
###Introduction
***

The Absorption Barrier is a new mechanic added for battle. Barrier Points, a new type of stat, provide a layer of protection for battlers. Any direct  damage that would normally be done to HP would be dealt to the battler’s Barrier Points first, mitigating any real damage dealt to the battler. Any remaining damage is then dealt to the battler.

屏障吸收是一个新的战斗技巧。屏障值是一个新的状态，为玩家提供一层保护。直接攻击将不会作用在血量上，而是先消减屏障值，剩余的在作用给玩家

There are various mechanics to exploit via this mechanic such as unexpiring barriers, expiring barriers, barrier penetration, barrier bypassing, etc. Read about it more in the next section~

借助这个可以开发很多功能，更多请看下一部分

***
###Barrier Points – Explanation
***

Barrier Points are a buffer placed on top of a battler’s HP. Any direct form of damage from skills or items will be dealt to the battler’s Barrier Points first before being dealt to the battler’s HP. Let’s see how the mechanics work in the following examples:

屏障值是一个血量增益状态。任何来自技能或者物品的攻击将会先削减屏障值。让我们看看它是怎么工作的

— Example 1 —-

For example, let’s assume the target has 100 Barrier Points. 150 damage is to be dealt to the target’s HP through a skill or item.

例如，这里有100屏障值，150伤害

150 DMG vs 100 Barrier Points: 50 DMG goes through

As a result, the target’s Barrier Points are reduced to 0 and the target’s HP will suffer only 50 DMG.

屏障值最后为0，受到50伤害

— Example 2—

The target has 100 Barrier Points. 50 damage is to be dealt to the target’s HP through a skill or item.

这里有100屏障值，50伤害

50 DMG vs 100 Barrier Points: 0 DMG goes through

As a result, the target’s Barrier Points are reduced to 50 and no damage goes through to the user’s HP.

屏障值最后为50，受到0伤害

***
###Barrier Penetration – Explanation
***

Some skills and items can possess a unique trait called Barrier Penetration. Barrier Penetration allows a percentile or flat amount of the damage to go through and ignore the target’s absorption barrier. The more Barrier Penetration on an action, the more of the target’s Barrier Points are ignored.

技能或者物品有个独特的特性叫做穿透屏障。这个允许部分伤害忽略屏障直接造成伤害

— Example —

The target has 500 Barrier Points. 100 damage is to be dealt to the target’s HP through a skill or item. The attacker has 75% Barrier Penetration.

这里有500屏障值，100伤害，75%穿透

100 DMG vs 500 Barrier Points: 75 DMG goes through

As a result, 75% of the damage will go through, meaning exactly 75 damage is dealt to the target’s HP. However, 25% of it gets absorbed by the target’s Barrier Points reducing the Barrier Points to 475 total.

屏障值最后为475，受到75伤害

***
###Unexpiring Barriers vs Timed Barriers – Explanation
***

There are two types of Absorption Barriers: Unexpiring Barriers and Timed Barriers. Unexpiring Barriers do not expire during the course of battle. The Barrier Points they acquire, if left untouched, will remain that value. On the other hand, Timed Barriers will last a certain amount of turns. When the turns reach 0 during the Regeneration Phase for the user, the Barrier Points are then stripped away.

这里有2种类型的屏障：永久屏障和临时屏障。

— Example —

Turn 1 – 100 Barrier Points
Turn 2 – 200 Barrier Points
Turn 3 – 300 Barrier Points

Right now, the user has 600 Barrier Points total. After the Regeneration Phase, it will become this:

Turn 1 – 200 Barrier Points
Turn 2 – 300 Barrier Points

And the user will have 500 Barrier Points total.

—

So, when damage is dealt, how do the Barrier Points absorb it? Damage is always dealt to the lowest turn, then the next lowest, etc. until it reaches the highest. After the highest, damage will then be dealt to Unexpiring Barrier Points. For example:

伤害优先给与最低回合数，然后慢慢变高，最后是永久屏障

— Example —

Turn 1 – 100 Barrier Points
Turn 2 – 200 Barrier Points
Unexpiring – 300 Barrier Points

Now, let’s suppose 500 damage will be dealt. It will result in this:

Turn 1 – 0 Barrier Points
Turn 2 – 0 Barrier Points
Unexpiring – 100 Barrier Points

***
###Notetags
***

Use the following notetags to alter the various mechanics of Barrier Points.

使用下面标签来设置

####Skill and Item Notetags:

	<User Barrier: +x>
	<User Barrier: -x>
	<Target Barrier: +x>
	<Target Barrier: -x>
This adjusts the Barrier Points for user or the target respectively by +x or -x. The Barrier Points altered for this notetag are unexpiring Barrier Points that do not remove themselves as time passes.

设置永久屏障值

	<User Barrier x Turns: +y>
	<User Barrier x Turns: -y>
	<Target Barrier x Turns: +y>
	<Target Barrier x Turns: -y>
This adjusts the Barrier Points for the user or target respectively at x turns by +y or -y amount. These Barrier Points will expire after x turns. Each turn goes by during the battler’s regeneration timing.

设置临时屏障值

	<Bypass Barrier>
This causes this skill to be able to bypass Barrier Points to directly deal damage to the target.

忽略屏障

	<Barrier Penetration: x%>
Causes x% of this skill or item’s damage to bypass the action target’s Barrier Points. If the target does not have enough Barrier Points, more damage will be dealt. This is a percentile value.

屏障穿透百分比

	<Barrier Penetration: x>
Causes x value of this skill or item’s damage to bypass action target’s Barrier Points. If the target does not have enough Barrier Points, more damage will be dealt. This is a flat value.

屏障穿透值

####Actor, Class, Enemy, Weapon, Armor, State Notetags:

	<Barrier Penetration: +x%>
	<Barrier Penetration: -x%>
This makes any damaging action by the attacker to have +x% or -x% bonus Barrier Penetration. This is a multiplicative bonus and applied before flat bonuses have been made.

屏障穿透百分比

	<Barrier Penetration: +x>
	<Barrier Penetration: -x>
This makes any damaging action by the attacker to have +x or -x bonus Barrier Penetration. This is a flat bonus and applied after multiplicative changes have been made.

屏障穿透值

	<Barrier Points: +x>
	<Barrier Points: -x>
The amount of unexpiring Barrier Points are gained at the start of a new battle for the affected user.

设置永久屏障值

	<Barrier Points x Turns: +y>
	<Barrier Points x Turns: -y>
The amount of Barrier Points are gained at the start of a new battle for the affected user that will last x turns.

设置临时屏障值

	<Barrier Regen: +x>
	<Barrier Regen: -x>
During the regeneration phase, the user will regenerate +x/-x unexpiring Barrier Points.

屏障更新值

	<Barrier Regen x Turns: +y>
	<Barrier Regen x Turns: -y>
During the regeneration phase, the user will regenerate Barrier Points that last x turns with a +y/-y value.

屏障每回合更新值

***
###Happy RPG Making!