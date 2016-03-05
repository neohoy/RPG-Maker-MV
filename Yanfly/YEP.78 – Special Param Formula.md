##YEP.78 – Special Param Formula
***
###Introduction
***
The values for Special Parameters: TGR, GRD, REC, PHA, MCR, TCR, PDR, MDR, FDR, and EXR are lesser used and lesser known, but are only modified by database object traits. This plugin enables you to utilize custom formulas for these Special Parameters to alter them in such a way where MAT can alter the MP Cost of skills and whatnot.

关于特殊能力参数的调整，包括TGR, GRD, REC, PHA, MCR, TCR, PDR, MDR, FDR, and EXR等是很少人指导的，而且仅仅可以通过数据库特性来调整。这个差距可以让你自定义这些的数值。

***
###Instructions – Special Parameter Explanation
***

Special Parameters differ from Extra Parameters in the sense that their base values are determined multiplicatively while Extra Parameters are determined in an additive form. For those who aren’t familiar with what the Special Parameters (sparams) do, this is a list that will explain their standard function in an RPG Maker MV project.

特殊参数是区分于额外参数。这里有一个列表来介绍特殊参数
—
####TGR – Target Rate 
– Against the standard enemy, the Target Rate value determines the odds of an enemy specifically targeting the user for a single target attack. At 0%, the enemy will almost never target the user. At 100%, it will have normal targeting opportunity. At 100%+, the user will have an increased chance of being targeted.  
*NOTE: For those using the Battle A.I. Core, any actions that have specific target conditions will bypass the TGR rate.  

目标概率：敌方攻击此目标概率。注意使用Battle A.I. Core插件将会忽略此概率

—
####GRD – Guard Effect  
– This is the effectiveness of guarding. This affects the guard divisor value of 2. At 100% GRD, damage will become ‘damage / (21.00)’. At 50% GRD, damage will become ‘damage / (20.50)’. At 200% GRD, damage will become ‘damage / (22.00)’ and so forth.

防御效果

—
####REC – Recovery Effect
– This is how effective heals are towards the user. The higher the REC rate, the more the user is healed. If a spell were to heal for 100 and the user has 300% REC, then the user is healed for 300 instead.

恢复效果

—
####PHA – Pharmacology
– This is how effective items are when used by the user. The higher the PHA rate, the more effective the item effect. If the user is using a Potion that recovers 100% on a target ally and the user has 300% PHA, then the target ally will receive healing for 300 instead.

药物治疗效果

—
####MCR – MP Cost Rate
– This rate affects how much MP skills with an MP Cost will require to use. If the user has 100% MCR, then the MP Cost will be standard. If the user has 50% MCR, then all skills that cost MP will cost only half the required MP. If the user has 200% MCR, then all skills will cost 200% their MP cost.

魔法消耗率

—
####TCR – TP Cost Rate
– This rate affects how much TP skills with an TP Cost will require to use. If the user has 100% TCR, then the TP Cost will be standard. If the user has 50% TCR, then all skills that cost TP will cost only half the required TP. If the user has 200% TCR, then all skills will cost 200% their TP cost.

TP值消耗率

—
####PDR – Physical Damage Rate
– This rate affects how much damage the user will take from physical damage. If the user has 100% PDR, then the user takes the normal amount. If the user has 50% PDR, then all physical damage dealt to the user is halved. If the user has 200% PDR, then all physical damage dealt to the user is doubled.

承受物理伤害率

—
####MDR – Magical Damage Rate
– This rate affects how much damage the user will take from magical damage. If the user has 100% MDR, then the user takes the normal amount. If the user has 50% MDR, then all magical damage dealt to the user is halved. If the user has 200% MDR, then all magical damage dealt to the user is doubled.

承受魔法伤害率

—
####FDR – Floor Damage Rate
– On the field map, this alters how much damage the user will take when the player walks over a tile that damages the party. The FDR value only affects the damage dealt to the particular actor and not the whole party. If FDR is at 100%, then the user takes the full damage. If FDR is at 50%, then only half of the damage goes through. If FDR is at 200%, then floor damage is doubled for that actor.

承受地面伤害率

—
####EXR – Experience Rate
– This determines the amount of experience gain the user whenever the user gains any kind of EXP. At 100% EXR, the rate of experience gain is normal. At 50%, the experience gain is halved. At 200%, the experience gain for the user is doubled.

经验获得率

—

***
###Instructions – Custom Formulas
***

The values calculated by the formulas in the plugin parameters are to come out as float values. If the result value comes out as 0.1 for GRD, it will be 10% GRD. Here is an example:

这个值可以通过公式实现浮动计算。这里有一个例子

	(base + plus)rate + flat + user.def / 1000

The ‘user.def / 1000’ is inserted at the end. Assuming everything else comes out to be 10% and the user’s DEF parameter is at 500, it will be 0.1 + 0.5 which means the total comes out to 0.6, hence a 60% GuaRD Effect.

***
###Instructions – Understanding Formula Variables
***

So, what does the ‘base’, ‘plus’, ‘rate’, and ‘flat’ mean in the formulas? This section will answer that in detail.

所以公式里面代表什么呢，这里是详细解答

Default plugin formula: 

	(base + plus)rate + flat

####BASE
– This value is determined by the default way RPG Maker MV determines the value for that stat, and the way RPG Maker MV determines it for Special Parameters (sparams) is by multiplying them all together with a base value of 1. This means if you have multiple traits with 80%, 50%, and 120%, then the multiplicative value of it comes out to 48%.

基础值：综合特性所有概率

####PLUS
– This is a new variable added by this plugin. Its purpose is to function as an addition to the base value. This addition can be done independently of database items as you can do a user.addSParam to alter the base value of the extra parameter. If using the default formula, this value is added to the base before any rates are multiplied by it and any flats added to the total.

增加值：由插件提供的值，用来增加基础值

####RATE
– This is a new variable added by this plugin. Its purpose is to function as a multiplicative modifier for the extra parameter value. This multiplicative value is determined by various database objects through notetags. If using the default formula, this value is multipled to the sum of the base and plus values of the extra parameter before the flat is added to the total.

概率值：由插件提供的值，用来调整基础值和增加值

####FLAT
– This is a new variable added by this plugin. Its purpose is to function as an additive modifier for the extra parameter value. This additive value is determined by various database objects through notetags. If using the plugin default formula, this value is added after the sum of the base and plus values of the extra parameter stat are multiplied by the rate value.

定值：由插件提供的值，用来调整前面的值

***
###Examples – Sample Formulas
***
The following are some sample formulas you can use to make the special parameters a bit more dynamic:

下面是一些例子

— GRD —
Math.max((base + plus)rate + flat + (user.def / 1000), 0.0000000001)
– This will cause the GRD effect to gain more damage reduction from DEF.

— REC —
(base + plus)rate + flat + ((user.def + user.mdf) / 2000)
– This will increase the user’s recovery rate from DEF and MDF.

— MCR —
(base + plus)rate + flat – (user.mat / 3000)
– This will cause the MP cost to reduce from the user having more MAT.

— TCR —
(base + plus)rate + flat – (user.atk / 3000)
– This will cause the TP cost to reduce from the user having more ATK.

— PDR —
(base + plus)rate + flat – (user.def / 4000)
– This will cause the user to take less physical damage by having more DEF.

— MDR —
(base + plus)rate + flat – (user.mdf / 4000)
– This will cause the user to take less magical damage by having more MDF.

The above are some examples on how you can make your special parameters to be affected by the other stats from the user.

上面的例子是借助玩家的状态来改变玩家特殊能力参数

***
###Notetags
***

You can use the following notetags to alter the various aspects that modify the special parameter values:

你可以使用标签来设置

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<stat Plus: +x%>
	<stat Plus: -x%>
	<stat Plus: +x.y>
	<stat Plus: -x.y>
Replace ‘stat’ with ‘tgr’, ‘grd’, ‘rec’, ‘pha’, ‘mcr’, ‘tcr’, ‘pdr’, ‘mdr’, ‘fdr’, or ‘exr’. This is the value added to the base parameter before the rate and flat values contribute to the total parameter value assuming the plugin’s default formula is utilized.

状态增加值

	<stat Rate: x%>
	<stat Rate: x.y>
Replace ‘stat’ with ‘tgr’, ‘grd’, ‘rec’, ‘pha’, ‘mcr’, ‘tcr’, ‘pdr’, ‘mdr’, ‘fdr’, or ‘exr’. This is the value multipled to the sum of the base and plus values of the parameter before added by the flat value assuming the plugin’s default formula is utilized.

状态概率值

	<stat Flat: +x%>
	<stat Flat: -x%>
	<stat Flat: +x.y>
	<stat Flat: -x.y>
Replace ‘stat’ with ‘tgr’, ‘grd’, ‘rec’, ‘pha’, ‘mcr’, ‘tcr’, ‘pdr’, ‘mdr’, ‘fdr’, or ‘exr’. This is the value added finally to the sum of the base and plus values after being multiplied by the rate value assuming the plugin’s default formula is utilized.

状态定值

***
###Happy RPG Making!