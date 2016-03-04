##YEP.71 – Life Steal
***
###Introduction
***
Life Steal is a mechanic in RPG Maker MV that only exists in the form of specific skills or items. There is no way to passively gain Life Steal from physical, magical, or certain hit attacks. This plugin will allow you to set passive Life Steal traits for physical, magical, and certain hit attacks for both HP and MP values.

生命偷取在MV里是特殊技能或者物品才可以使用的。无法从物理攻击中获得。这个插件可以让你设置主动生命偷取，包括血量和魔法量

***
###Notetags

You can use the following notetags to alter how Life Stealing works for the various database entries.

你可以使用下面标签来改变生命偷取的选项

####Skill and Item Notetags:

	<HP Life Steal: x%>
	<MP Life Steal: x%>
This causes this attack to life steal x% of HP or MP back relative to the amount of damage dealt.

设置偷取百分比

	<HP Life Steal: x>
	<MP Life Steal: x>
This causes this attack to life steal exactly x amount of HP or MP back regardless of damage dealt.

设置偷取值

	<Cancel Life Steal>
Makes this skill or item cancel any Life Steal effects from passively activating for this action. However, HP Drain and MP Drain will still still occur.

取消生命偷取

	<Cancel HP Life Steal>
	<Cancel MP Life Steal>
Specifically cancels out HP Life Steal or MP Life Steal effects from passively activating for this action. However, HP Drain and MP Drain will still occur.

单独取消血量偷取或者魔法量偷取

####Actor, Class, Enemy, Weapon, Armor, State Notetags:

	<HP Life Steal Physical: +x%>
	<HP Life Steal Magical: +x%>
	<HP Life Steal Certain: +x%>

	<MP Life Steal Physical: +x%>
	<MP Life Steal Magical: +x%>
	<MP Life Steal Certain: +x%>

	<HP Life Steal Physical: -x%>
	<HP Life Steal Magical: -x%>
	<HP Life Steal Certain: -x%>

	<MP Life Steal Physical: -x%>
	<MP Life Steal Magical: -x%>
	<MP Life Steal Certain: -x%>
This causes the related battler to multiplicatively increase its passive Life Steal by +x% or -x% of the damage dealt towards Physical, Magical, or Certain Hit type of attacks. This effect stacks multiplicatively.

设置相应的生命偷取率

	<HP Life Steal Physical: +x>
	<HP Life Steal Magical: +x>
	<HP Life Steal Certain: +x>

	<MP Life Steal Physical: +x>
	<MP Life Steal Magical: +x>
	<MP Life Steal Certain: +x>

	<HP Life Steal Physical: -x>
	<HP Life Steal Magical: -x>
	<HP Life Steal Certain: -x>

	<MP Life Steal Physical: -x>
	<MP Life Steal Magical: -x>
	<MP Life Steal Certain: -x>
This causes the related battler to additively increase its passive Life Steal by a flat +x or -x of the damage dealt towards Physical, Magical, or Certain Hit type of attacks. This effect stacks additively.

设置相应的生命偷取值

	<Guard Life Steal>
The related battler cannot be life stolen from for both HP and MP.

抵挡生命偷取

	<Guard HP Life Steal>
	<Guard MP Life Steal>
The related battler cannot be life stolen from for either HP or MP.

单独抵挡血量或魔法量偷取

	<Cancel Life Steal>
The related battler cannot passively life steal both HP and MP.

取消生命偷取

	<Cancel HP Life Steal>
	<Cancel MP Life Steal>
The related battler cannot passively life steal HP or MP specifically.

单独取消血量或魔法量偷取

***
###Happy RPG Making!