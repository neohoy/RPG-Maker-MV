##YEP.56 – Limited Skill Uses

***
###Introduction
***

This plugin requires YEP_SkillCore. Make sure this plugin is located under YEP_SkillCore in the plugin list.

这个插件需要YEP_SkillCore，请确保它放在YEP_SkillCore下面

This plugin enables you to set a limited amount of times certain skills (or all skills) can be used per battle or ever. This adds a different type of skill currency and balance mechanic in limiting the amount of times a skill can be used without directly having alter MP, TP, or the like.

这是技能核心插件拓展插件，能够让你限制一些技能的使用次数。添加了一个不同的技能类型，并且平衡了技能使用的限制次数

***
###Notetags
***

You can use these notetags to govern the various Limited Uses aspects of your skills.

你可以使用下面标签来给你的技能设置不同的使用限制

####Skill Notetags:

	<Unlimited Use>
If you’ve enabled ‘Limit All Skills’ in the plugin parameters, this will forcefully make the skill unlimited use. If you use this notetag, it will override any of the Limited Use settings.

如果你开启了“限制所有技能”选项，那么这个将会让技能不受限制使用，如果你使用了这个标签，它将会重写你的限制设置

	<Limit Uses: x>
This will set the number of times the skill can be used to x. If the skill has 0 charges left, the skill cannot be used.

设置技能限制使用次数，如果为0，则不能使用

	<Recover All Uses>
	<Not Recover All Uses>
When using the recover all command, depending on the settings within the plugin parameters, all limited use charges are recovered or not. These notetags will enable you to utilize the other setting for the skill.

当你使用恢复所以的命令，取决插件设置，所有限制将被恢复。这些标签将会让你使用技能的其他设置

	<Victory Uses Recover: x>
	<Escape uses Recover: x>
	<Lose Uses Recover: x>
When the player wins a battle, escapes a battle, or loses a battle, the skill use will recover x amount of uses for the respective outcome. If the notetags aren’t used, the amounts restored will be equal to settings made in the plugin’s parameters.

当玩家获得胜利，逃跑或者失败的时候，技能恢复使用次数

	<After Battle Uses Recover: x>
This will set the recovery rate of victory, escape, or loss of battle to be equal to x indiscriminately.

当玩家完成战斗后恢复技能使用次数

####Skill and Item Notetags:

	<Global Limited Uses: +x>
	<Global Limited Uses: -x>
This will change the target’s limited uses by +x or -x for all skills. +x will increase the amount of times the skills can be used. -x will decrease the amount of times the skills can be used.

对技能改变使用次数。+x将会增加，-x将会减少

	<SType x Limited Uses: +y>
	<SType x Limited Uses: -y>
This will change the target’s limited uses by +y or -y for all skills of the skill type x. +y will increase the amount of times the skills can be used. -y will decrease the amount of times the skills can be used.

改变技能类型x的技能使用次数y。+y将会增加，-y将会减少

	<Skill x Limited Uses: +y>
	<Skill x Limited Uses: -y>
	<Skill name Limited Uses: +y>
	<Skill name Limited Uses: -y>
This will change the target’s limited uses by +y or -y for skill x. If you use the named notetag varient and have multiple skills in the database with the same name, priority will be given to the skill with the highest ID. +y will increase the amount of times the skills can be used. -y will decrease the amount of times the skills can be used.

改变技能x的使用次数y。如果你使用了名字标签，则会优先生效ID最高的。+y将会增加，-y将会减少

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Global Use Max: +x>
	<Global Use Max: -x>
A battler affected by this property will have any Limited Use skills alter the maximum times used by +x or -x.

改变最大使用次数

	<SType x Use Max: +y>
	<SType x Use Max: -y>
A battler affected by this property will have Limited Use skills from skill type x alter the maximum times used by +y or -y.

改变技能类型x的最大使用次数

	<Skill x Use Max: +y>
	<Skill x Use Max: -y>
	<Skill name Use Max: +y>
	<Skill name Use Max: -y>
A battler affected by this property will have Limited Use for skill x (or named if you’re using that version of the notetag instead) alter the maximum times used by +y or -y. If you are using the named version of the notetag and have multiple skills in the database with the same name, then priority will be given to the skill with the highest ID.

改变技能x的最大使用次数。

***
###Happy RPG Making!

