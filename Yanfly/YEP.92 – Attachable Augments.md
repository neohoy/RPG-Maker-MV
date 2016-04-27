##YEP.92 – Attachable Augments
***
###Introduction
***

This plugin requires YEP_ItemCore. Make sure this plugin is located under YEP_ItemCore in the plugin list.

这个插件需要YEP_ItemCore，确保放在它下面

Attachable Augments is an extension plugin made for the Item Core plugin. It allows equipment to be able to attach augment components to various slots, that you can define individually per item. These slots can be of a certain category unique to that item or global across all items. The effects used with the augment can involve parameter changes, adding skills, adjust state resistances, place attack elements, and more!

附加增强系统是物品核心插件的拓展插件。他可以让你的装备能够镶嵌附加不同的能力，你可以自定义每个独立物品。这些镶嵌口可以设置独特的分类，我们可以通过这些改变基础参数，增加技能，调整抗性等等

***
###Notetags
***

You can use the following notetags to setup how augments work in your game and affect your equipment.

可用标签

####Weapon and Armor Notetags:

	<Augment Slots>
	Rune
	Glyph
	Orb
	Mark
	</Augment Slots>
This allows you to set what kind of augments are used for the item. The names used for the augment slots are the augment types used for that item.
设置装备镶嵌槽类别

	<No Augment Slots>
This makes the item have no augment slots.
无法镶嵌附加

####Item, Weapon, Armor Notetags

	<Augment: type>
	augment effect
	augment effect
	</Augment: type>
This will change the item into a non-Independent item. This item can be used to augment equipment that contain the appropriate augment ‘type’. This particular notetag will decide the augment effect for attaching the augment component and the reverse effect for detaching the component. Insert multiple sets of these notetags to allow different augment effects when used on different augment slot types.

将物品改造为非独立物品，这些物品可以用来镶嵌在武器护甲上。这个标签可以用来设置镶嵌后的属性并且脱离后也会保留状态。你可以设置多个效果影响

	<Augment Attach: type>
	augment effect
	augment effect
	</Augment Attach: type>
This will change the item into a non-Independent item. This item can be used to augment equipment that contain the appropriate augment ‘type’. This notetag will decide only the augment effects that are applied when the augment component is attached to the equipment and not when detached. Insert multiple sets of these notetags to allow different augment effects when used on different augment slot types.

将物品改造为非独立物品，这些物品可以用来镶嵌在武器护甲上。这个标签可以用来设置镶嵌后的属性但是脱离后不会保留状态。你可以设置多个效果影响

	<Augment Detach: type>
	augment effect
	augment effect
	</Augment Detach: type>
This will change the item into a non-Independent item. This item can be used to augment equipment that contain the appropriate augment ‘type’. This notetag will decide only the augment effects that are applied when the augment component is detached from the equipment and not attached. Insert multiple sets of these notetags to allow different augment effects when used on different augment slot types.

将物品改造为非独立物品，这些物品可以用来镶嵌在武器护甲上。这个标签可以用来设置脱离镶嵌后的属性，注意在镶嵌时不会保留状态。你可以设置多个效果影响

***
###Augment Effect List
***

The following is a list of effects you can use for the <Augment: type>, <Augment Attach: type>, <Augment Detatch: type> notetags to have it apply the desired effects to the upgraded item.

镶嵌后效果列表

— Effects —

	Param: +x
	Param: -x
– Replace ‘Param’ with ‘MaxHP’, ‘MaxMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, or ‘LUK’. This will increase/decrease the parameter for the item by x.

改变基础属性参数

—

	Param: +x%
	Param: -x%
– Replace ‘Param’ with ‘MaxHP’, ‘MaxMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, ‘LUK’, ‘HIT’, ‘EVA’, ‘CRI’, ‘CEV’, ‘MEV’, ‘MRF’, ‘CNT’, ‘HRG’, ‘MRG’, ‘TRG’, ‘TGR’, ‘GRD’, ‘REC’, ‘PHA’, ‘MCR’, ‘TCR’, ‘PDR’, ‘MDR’, ‘FDR’, or ‘EXR’. This will increase/decrease the rate for that parameter for the item by x%. Refer to the Base Parameter Control, Extra Parameter Formula, and Special
Parameter Formula plugins for more information regarding these stats.

按照百分比改变基础属性参数

—

	Boost: +x
	Boost: -x
– This will increase or decrease the boost count of the item by x.

改变物品数量
—

	Price: +x
	Price: -x
– This will increase or decrease the price of the item by x.

改变物品价格

—

	Cannot Detach
– This makes the augment unable to be detached once applied.

不可脱离镶嵌

—

	Add Attack Element: x
	Remove Attack Element: x
– Add/Remove Attack Element ‘x’ to item. You can use either the name or the ID of the element. If the name is used and you have multiple elements in your database with the same name, priority will be given to the element with the highest ID.

改变攻击属性

—

	Add Attack State: x
	Add Attack State: x, y%
	Remove Attack State: x
	Remove Attack State: x, y%
– Add/Remove Attack State ‘x’ to item. You can use either the name of the ID of the state. If the name is used and you have multiple states in your database with the same name, priority will be given to the state with the highest ID. If ‘y’ is used, then the success rate of landing the state will be y%. If ‘y’ is not used, the success rate of landing the state is 100%.

改变攻击状态

—

	Add Debuff Rate: param, x%
	Remove Debuff Rate: param, x%
– Replace ‘param’ with ‘MaxHP’, ‘MaxMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, or LUK. Add/remove the debuff affliction rate of the parameter for the item to ‘x%’ rate.

改变效果概率

—

	Add Element Rate: x, y%
	Remove Element Rate: x, y%
– Add/Remove element rate ‘x’ to item. You can use either the name or the ID of the element. If the name is used and you have multiple elements in your database with the same name, priority will be given to the element with the highest ID. The item’s element rate for ‘x’ will be ‘y%’ rate.

改变元素概率

—

	Add Passive State: x
	Remove Passive State: x
– Requires YEP_AutoPassiveStates.js installed. Add/Remove passive state ‘x’ to item. You can use either the name or the ID of the state. If the name is used and you have multiple states in your database with the same name, priority will be given to the state with the highest ID.

改变被动效果

—

	Add Skill: x
	Remove Skill: x
– Add/Remove skill ‘x’ to item. You can use either the name or the ID of the skill. If the name is used and you have multiple skills in your database with the same name, priority will be given to the skill with the highest ID. This will make the skill temporarily usable by the actor as long as the item is equipped with the augment on it.

改变技能

—

	Add Skill Type: x
	Add SType: x
	Remove Skill Type: x
	Remove SType: x
– Add/Remove skill type ‘x’ to item. You can use either the name or the ID of the skill type. If the name is used and you have multiple skills in your database with the same name, priority will be given to the skill type with the highest ID. This will make the skill type temporarily usable by the actor as long as the item is equipped with the augment on it.

改变技能类型

—

	Add State Rate: x, y%
	Remove State Rate: x, y%
– Add/Remove state rate for state ‘x’ to item. You can use either the name or the ID of the state. If the name is used and you have multiple states in your database with the same name, priority will be given to the state with the highest ID. The item’s state rate for ‘x’ will be ‘y%’ rate.

改变状态概率

—

	Add State Resist: x
	Remove State Resist: x
– Add/Remove state resist for state ‘x’ to item. You can use either the name or the ID of the state. If the name is used and you have multiple states in your database with the same name, priority will be given to the state with the highest ID.

改变状态抵抗率

—

	Change Base Name: x
	Cancel Base Name: x
– Changes/Cancels the base name of the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the base name, then priority is given to the first augment that alters the base name.

改变物品基础名字

—

	Change Icon: x
	Cancel Icon: x
– Changes/cancels the icon of the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the icon, then priority is given to the first augment that alters the icon.

改变图标

—

	Change Prefix: x
	Cancel Prefix: x
– Changes/Cancels the prefix of the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the prefix, then priority is given to the first augment that alters the priority.

改变前缀

—

	Change Priority Name: x
	Cancel Priority Name: x
– Changes/Cancels the priority name of the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the priority name, then priority is given to the first augment that alters the priority name.

改变优先名

—

	Change Suffix: x
	Cancel Suffix: x
– Changes/Cancels the suffix of the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the suffix, then priority is given to the first augment that alters the suffix.

改变后缀

—

	Change Text Color: x
	Cancel Text Color: x
– Changes/Cancels the text color used for the item to ‘x’ while the augment is on the item. If an item has multiple augments that alter the text color, then priority is given to the first augment that alters text color.

改变文本颜色

***
###Happy RPG Making!