##YEP.91 – Equip Skill Tiers
***
###Introduction
***

This plugin requires YEP_EquipBattleSkills. Make sure this plugin is located under YEP_EquipBattleSkills in the plugin list.

这个插件需要YEP_EquipBattleSkills，确保放在这个下面

This plugin imposes a limit upon actors to limit what skills can be equipped based on tiers. The player must abide by the limits before being able to exit the menu allowing for better control over gameplay balance.

这个插件给玩家提供了通过分类来限制技能的装备。玩家在退出菜单时必须遵循规则，这将更好的平衡游戏

***
###Notetags
***

The following are notetags that alter the tier settings of skills.

修改标签

####Skill Notetag

	<Skill Tier: x>
Sets the skill’s tier to x, making it limited by the restrictions applied by the actor.

设置技能分类

####Actor, Class, Skill, Weapon, Armor, and State Notetags

	<Skill Tier x Slots: +y>
	<Skill Tier x Slots: -y>
Increases or decreases the skill tier for tier x by y slots. The changes made here do not go under 0 nor do they bypass the maximum battle skills equip limit.

增加或减少技能分类数量

***
###Happy RPG Making!

