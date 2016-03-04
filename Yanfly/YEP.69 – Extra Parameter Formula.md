##YEP.69 – Extra Parameter Formula
***
###Introduction
***

The values for the Extra Parameters: HIT, EVA, CRI, CEV, MEV, MRF, CNT, HRG, MRG, and TRG, in RPG Maker MV are only able to be ever modified by traits by the various database objects. While it is flexible, RPG Maker MV does not enable you to utilize custom formulas to make things such as ATK and AGI influence HIT rate or LUK influence CRItical hits. With this plugin, now you can along with a few more goodies!

可以设置额外的参数值，以前这些参数只可以用特性来调整。同时MV本身不能让你自定义类似参数的公式。现在用这个差距，你可以单独做一些调整。

***
###Instructions – Extra Parameter Explanation
***

For those who aren’t familiar with what the Extra Parameters (xparams) do, this is a list that will explain their standard functions in an RPG Maker MV project.

对于那些不熟悉额外参数的人，这里是一个解释列表

—

HIT – Hit Rate%
– This determines the physical hit success rate of the any physical action. All physical attacks make a check through the HIT rate to see if the attack will connect. If the HIT value passes the randomizer check, the attack will connect. If the HIT value fails to pass the randomizer check, the attack will be considered a MISS.

HIT-物理攻击命中命中率。

—

EVA – Evasion Rate%
– This determines the physical evasion rate against any incoming physical actions. If the HIT value passes, the action is then passed to the EVA check through a randomizer check. If the randomizer check passes, the physical attack is evaded and will fail to connect. If the randomizer check passes, the attempt to evade the action will fail and the action connects.

EVA-回避攻击概率
—

CRI – Critical Hit Rate%
– Any actions that enable Critical Hits will make a randomizer check with this number. If the randomizer check passes, extra damage will be carried out by the initiated action. If the randomizer check fails, no extra damage will be added upon the action.

GRI-暴击率

—

CEV – Critical Evasion Rate%
– This value is put against the Critical Hit Rate% in a multiplicative rate. If the Critical Hit Rate is 90% and the Critical Evasion Rate is 20%, then the randomizer check will make a check against 72% as the values are calculated by the source code as CRI * (1 – CEV), therefore, with values as 0.90 * (1 – 0.20) === 0.72.

CEV-回避暴击率

—

MEV – Magic Evasion Rate%
– Where EVA is the evasion rate against physical actions, MEV is the evasion rate against magical actions. As there is not magical version of HIT, the MEV value will always be bit against when a magical action is initiated. If the randomizer check passes for MEV, the magical action will not connect. If the randomizer check fails for MEV, the magical action will connect.

MEV-魔法回避率

—

MRF – Magic Reflect Rate%
– If a magical action connects and passes, there is a chance the magical action can be bounced back to the caster. That chance is the Magic Reflect Rate. If the randomizer check for the Magic Reflect Rate passes, then the magical action is bounced back to the caster, ignoring the caster’s Magic Evasion Rate. If the randomizer check for the Magic Reflect Rate fails, then the magical action will connect with its target.

MRF-魔法反击率

—

CNT – Counter Attack Rate%
– If a physical action connects and passes, there is a chance the physical action can be avoided and a counter attack made by the user will land on the attacking unit. This is the Counter Attack Rate. If the randomizer check for the Counter Attack Rate passes, the physical action is evaded and the target will counter attack the user. If the randomizer check fails, the physical action will connect to the target.

CNT-攻击反击率

—

HRG – HP% Regeneration
– During a battler’s regeneration phase, the battler will regenerate this percentage of its MaxHP as gained HP with a 100% success rate.

HRG-血量回复率
—

MRG – MP% Regeneration
– During a battler’s regeneration phase, the battler will regenerate this percentage of its MaxMP as gained MP with a 100% success rate.

MRG-魔法量回复率

—

TRG – TP% Regeneration
– During a battler’s regeneration phase, the battler will regenerate this percentage of its MaxTP as gained TP with a 100% success rate.

TRG-时间点数回复率

—

***
###Instructions – Custom Formulas
***

The values calculated by the formulas in the plugin parameters are to come out as float values. If the result value comes out as 0.1 for CRI, it will be 10% CRI. Here is an example:

可以通过浮动的数值，利用公式计算这些值。如果最后结果是GRI=0.1,则概率为10%。

	(base + plus) * rate + flat + user.luk / 1000

The ‘user.luk / 1000’ is inserted at the end. Assuming everything else comes out to be 10% and the user’s LUK parameter is at 500, it will be 0.1 + 0.5 which means the total comes out to 0.6, hence a 60% CRItical hit rate.


***
###Instructions – Understanding Formula Variables
***

So, what does the ‘base’, ‘plus’, ‘rate’, and ‘flat’ mean in the formulas? This section will answer that in detail.

所以公式里面那些值是代表什么呢。这里会回答这个问题

Default plugin formula: 

	(base + plus) * rate + flat

BASE
– This value is determined by the default way RPG Maker MV determines the value for that stat, and the way RPG Maker MV determines it is by adding up the total trait values of that stat. If a battler would have a mixture of +95%, -10%, and +5% HIT traits, then the base stat value would be +90%.

基础值

PLUS
– This is a new variable added by this plugin. Its purpose is to function as an addition to the base value. This addition can be done independently of database items as you can do a user.addXParam to alter the base value of the extra parameter. If using the default formula, this value is added to the base before any rates are multiplied by it and any flats added to the total.

通过插件增加的增量

RATE
– This is a new variable added by this plugin. Its purpose is to function as a multiplicative modifier for the extra parameter value. This multiplicative value is determined by various database objects through notetags. If using the default formula, this value is multipled to the sum of the base and plus values of the extra parameter before the flat is added to the total.

通过插件增加的概率

FLAT
– This is a new variable added by this plugin. Its purpose is to function as an additive modifier for the extra parameter value. This additive value is determined by various database objects through notetags. If using the plugin default formula, this value is added after the sum of the base and plus values of the extra parameter stat are multiplied by the rate value.

通过插件增加的定值

***
###Notetags
***

You can use the following notetags to alter the various aspects that modify the extra parameter values:

你可以使用下面的标签来调整

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<stat Plus: +x%>
	<stat Plus: -x%>
	<stat Plus: +x.y>
	<stat Plus: -x.y>
Replace ‘stat’ with ‘hit’, ‘eva’, ‘cri’, ‘cev’, ‘mev’, ‘mrf’, ‘cnt’, ‘hrg’, ‘mrg’, or ‘trg’. This is the value added to the base parameter before the rate and flat values contribute to the total parameter value assuming the plugin’s default formula is utilized.

设置增量

	<stat Rate: x%>
	<stat Rate: x.y>
Replace ‘stat’ with ‘hit’, ‘eva’, ‘cri’, ‘cev’, ‘mev’, ‘mrf’, ‘cnt’, ‘hrg’, ‘mrg’, or ‘trg’. This is the value multipled to the sum of the base and plus values of the parameter before added by the flat value assuming the plugin’s default formula is utilized.

设置概率

	<stat Flat: +x%>
	<stat Flat: -x%>
	<stat Flat: +x.y>
	<stat Flat: -x.y>
Replace ‘stat’ with ‘hit’, ‘eva’, ‘cri’, ‘cev’, ‘mev’, ‘mrf’, ‘cnt’, ‘hrg’, ‘mrg’, or ‘trg’. This is the value added finally to the sum of the base and plus values after being multiplied by the rate value assuming the plugin’s default formula is utilized.

设置定值

***
###Happy RPG Making!