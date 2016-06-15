##YEP.107 – Element Core – RPG Maker MV
***
###Introduction
***
Elemental control in RPG Maker MV is pretty lacking. The calculation of how multiple elements are handled aren’t very clear nor are they too intuitive when it comes to certain aspects. This plugin also gives way to skills and items having more than one element, battlers being able to absorb, reflect, amplify elemental damage, and more!

元素控制在RPG Maker MV里面是非常缺乏的。我们很难明白多少类型的元素被触发，我们有时候在某些方面只能凭直觉判断。这个插件可以让你的技能或者物品有多个元素属性，战斗者可以吸收，反弹或者增强伤害等。

* Note: If you are using the Element Reflect and/or Element Absorb plugins, remove them if you are planning on using this plugin. Don’t worry. This plugin uses the same exact notetag format as those two.  
如果你使用了 Element Reflect和Element Absorb插件，请关闭他们。不用担心会有什么影响，这个插件使用了和他们一样的标签命令

* Note: If you are using the Battle Engine Core, place this plugin under the Battle Engine Core in the plugin list for additional features.  
如果你使用了Battle Engine Core，请把这个插件放在它下面来获得更多功能特点。

* Note: If you are using the Damage Core, place this plugin underneath the Damage Core plugin in the list for maximum compatibility.  
如果你使用了Damage Core，把这个插件放在它下面来提高兼容性

***
###Notetags
***
Use these notetags if you wish to modify various aspects of elements for your database objects.

你可以使用下面标签来调整数据库里和元素相关的内容

####Skill and Item Notetags

	<Bypass Element Reflect>
– Allows this skill/item to ignore elemental reflect properties. This will not bypass reflect properties as a whole, however.

忽略元素反弹

	<Multiple Elements: x>
	<Multiple Elements: x to y>
	<Multiple Elements: x, x, x>
	<Multiple Elements: name, name, name>
– This adds elements x (or name) to the skill/item in addition to the skill/item’s current element. Skills and items with multiple elements will follow the Multi-Element Rule when calculating damage rate. Insert more of this notetag to insert more elements.

给技能或者物品增加元素种类，他们将会服从混合元素规则

	<Multi-Element Rule: Lowest>
	<Multi-Element Rule: Add>
	<Multi-Element Rule: Multiply>
	<Multi-Element Rule: Highest>
	<Multi-Element Rule: Average>
– This allows you to set the rule for this skill/item if it has multiple elements. Either the lowest rate, the additive sum of all rates, the multiplicative product of all rates, or the highest rate will be used. If average is used, it will be the average of all element rates.

这些规则可以用来限制多元素。包括取最低值，叠加，乘积，最高值，平均等

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Element Absorb: x>
	<Element Absorb: x, x, x>
	<Element Absorb: name>
	<Element Absorb: name, name, name>
– Causes element x to be absorbed and heals the battler. When an element is absorbed, the rate goes down by 200% instead of being just an inverse. This is so that battlers that are originally resistant to the element will absorb more of the element while battlers that are originally vulnerable to the element will absorb less of the element. The minimum amount
absorbed is 0.01%.

设置元素吸收。当某个元素被吸收时，比率将会下降200%而不是仅仅是个倒数。这意味着抵抗力强的将吸收更多伤害，抵抗力弱的吸收较少伤害。最小值是0.01%

	<Element Reflect x: +y%>
	<Element Reflect x: -y%>
	<Element Reflect name: +y%>
	<Element Reflect name: -y%>
– Increases or decreases the rate to reflect element x by y%. If a skill or item has multiple elements, the reflect rate is added for each element used by the skill/item.

设置元素反射。如果技能或者物品有多个元素，反射率会叠加

	<Element Amplify x: +y%>
	<Element Amplify x: -y%>
	<Element Amplify name: +y%>
	<Element Amplify name: -y%>
– If the user performs a skill or item that utilizes element x (or name), increase or decrease its damage by y%. If a skill or item has multiple elements, the rate is increased additively for each element.
设置元素增强。如果技能或者物品有多个元素，增强率会叠加

	<Element Null>
– This will cause the battler to not have elemental attacks when using skills and items. However, this will not bypass the ‘Force Element’ action sequence effect.

设置无元素，但是这并不会忽略战斗序列里面的强制元素

	<Force Element x Rate: y%>
	<Force Element name Rate: y%>
– This forces the battler’s elemental rate for x (or named) to be y%. This will work in a priority setting of states (highest priority to lowest), equips (first to last), then class, then actor/enemy if more than one notetag is used for the same element. If y is negative, the element is absorbed.

设置强制元素。这个的优先级为状态、装备、职业、角色或敌群。如果y是负值，则该元素会被吸收

***
###Yanfly Engine Plugins – Battle Engine Extension – Action Sequence Commands
***

If you have YEP_BattleEngineCore.js installed with this plugin located underneath it in the Plugin Manager, you can make use of these extra damage related action sequences.

如果你使用了YEP_BattleEngineCore。你可以使用下面的命令

	ADD ELEMENT: X
	ADD ELEMENT: X, X, X
	ADD ELEMENT: NAME
	ADD ELEMENT: NAME, NAME, NAME

This will add more elements to the currently existing elements. This will not include forced elements.

这会增加元素

Usage Example: 

	add element: 4
	add element: 5, 6, 7
	add element: fire
	add element: ice, wind, water  
***
	CLEAR ELEMENT

This will clear any ___ Element action sequence settings and revert element calculation back to normal.

这会清除元素

Usage Example: 
	
	clear element
***
	
	FORCE ELEMENT: X
	FORCE ELEMENT: X, X, X
	FORCE ELEMENT: NAME
	FORCE ELEMENT: NAME, NAME, NAME

This will override elemental settings for elemental damage rate calculations except for customized calculations that aim at specific elements. This will ignore all other elements.

除了额外自定义的元素计算公式，这会覆盖元素设置

Usage Example: 

	force element: 4
	force element: 5, 6, 7
	force element: fire
	force element: ice, wind, water
***

	NULL ELEMENT

This will force the elements to null. Calculated elemental damage will always return neutral rate. Using this will clear the Force Element action sequence effect.

这会强制元素为空

Usage Example: 

	null element

***
###Happy RPG Making!

