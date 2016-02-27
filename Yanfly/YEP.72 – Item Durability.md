##YEP.72 – Item Durability

***
###Introduction
***

This plugin requires YEP_ItemCore. Make sure this plugin is located under YEP_ItemCore in the plugin list.

这个插件需要YEP_ItemCore，确保它放在YEP_ItemCore下面

Independent Weapons and Armors will now have a Durability value. Over the course of battle, equipment durability will drop based on actions performed, damage taken, and the like. When a piece of equipment’s durability value reaches 0, the piece of equipment will break. Durability can be repaired by items and increased by skills, too.

独立武器和装备现在有了耐久度。通过战斗进程，装备耐久度将会根据战斗行动，受到伤害或者类似的降低耐久度。当你件装备耐久度降为0，这个装备会破损。耐久度可以被物品修复或被技能提升。

***
###Notetags
***

The following notetags can be used to adjust item durability for equipment.

下面的标签可以被用来调整装备耐久度

####Weapon and Armor Notetags:

	<Durability: x>
This sets the item’s default durability value to x. This is the starting durability value for the item. If this notetag isn’t used, the independent equipment will refer to the value in the plugin parameters.

设置物品默认耐久度。这是初始值。如果没有设置，则会使用插件默认设置。

	<Durability Variance: x>
This alters the starting durability value with a variance of x. This means there can be a variance of -x to +x for the durability starting value.

改变物品初始耐久度。你可以用增加或者减少

	<Durability Maximum: x>
This is the maximum durability value the independent equipment can have. When repairing durability, the item’s durability value cannot exceed this amount. This amount is dependent on the base item’s durability value.

物品最大耐久度。当修复耐久度时，物品不能超过值。

	<Bypass Durability>
	<Unbreakable>
This sets the item to not have bypass the durability system and making the independent item unbreakable.

设置物品不消耗耐久度并且不让物品破损

	<Break Sound Name: filename>
	<Break Sound Volume: x>
	<Break Sound Pitch: x>
	<Break Sound Pan: +x>
	<Break Sound Pan: -x>
This changes the sound effect played when using this piece of equipment is broken in battle. Filenames are case sensitive and do not include the file extension into the filename.

这是物品破损时播放的声音。设置名字不包含拓展名

####Item, Weapon, Armor Notetags:

	<Repair Durability: x>
This will repair any weapon or armor’s durability by x. The repair effect is accessed from the weapon or armor’s action menu.

修复耐久度

	<Repair Weapon: x>
	<Repair Armor: x>
This will specifically repair only weapons or armors by x amount. The repair effect is accessed from the weapon or armor’s action menu.

仅仅修复武器或者装备

	<Repair WType x: y>
	<Repair AType x: y>
This will specifically repair only weapon-type x or armor-type x by y amount. The repair is accessed from the weapon or armor’s action menu.

修复武器类型x和装备类型x的耐久度

	<Repair Sound Name: filename>
	<Repair Sound Volume: x>
	<Repair Sound Pitch: x>
	<Repair Sound Pan: +x>
	<Repair Sound Pan: -x>
This changes the sound effect played when using this item to repair the durability of another item.

修复播放声音

	<Unbreakable Durability>
Removes the equipment’s durability and makes it unbreakable.

移走耐久度并且让装备不再破损

	<Unbreakable Weapon>
	<Unbreakable Armor>
Removes the weapon or armor’s durability and makes it unbreakable.

移走武器和装备的耐久度并且不再破损

	<Unbreakable WType x>
	<Unbreakable AType x>
Removes durability for specifically weapon-type x or armor-type x and makes it unbreakable. Filenames are case sensitive and do not include the file extension into the filename.

移走武器类型x和装备类型x的耐久度并且不再破损

####Skill and Item Notetags:

	<User Weapon Durability: +x>
	<User Weapon Durability: -x>
Each hit of this skill/item will cause all of the user’s weapon(s) durability to be altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少耐久度x，如果到达0，则武器破损

	<User All Weapon Durability: +x>
	<User All Weapon Durability: -x>
Each hit of this skill/item will cause all of the user’s weapon(s) durability to be altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少所有武器的耐久度x，如果到达0，则武器破损

	<User Random Weapon Durability: +x>
	<User Random Weapon Durability: -x>
Each hit of this skill/item will cause a random weapon equipped by the user to have its durability altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少随机武器的耐久度x，如果到达0，则武器破损

	<User Armor Durability: +x>
	<User Armor Durability: -x>
Each hit of this skill/item will cause the user’s armor(s) durability to be altered by +x or -x. Depending on the ‘Damage All’ plugin parameter, this will affect either all armors or affect a random armor piece. If the item reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少装备的耐久度x，如果到达0，则装备破损

	<User All Armor Durability: +x>
	<User All Armor Durability: -x>
Each hit of this skill/item will cause all of the user’s armor(s) durability to be altered by +x or -x. If it reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少所以装备的耐久度x，如果到达0，则装备破损

	<User Random Armor Durability: +x>
	<User Random Armor Durability: -x>
Each hit of this skill/item will cause a random armor equipped by the user to have its durability altered by +x or -x. If it reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少随机装备的耐久度x，如果到达0，则装备破损

	<Target Weapon Durability: +x>
	<Target Weapon Durability: -x>
Each hit of this skill/item will cause all of the target’s weapon(s) durability to be altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少目标武器的耐久度x，如果到达0，则武器破损

	<Target All Weapon Durability: +x>
	<Target All Weapon Durability: -x>
Each hit of this skill/item will cause all of the target’s weapon(s) durability to be altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少所有目标武器的耐久度x，如果到达0，则武器破损

	<Target Random Weapon Durability: +x>
	<Target Random Weapon Durability: -x>
Each hit of this skill/item will cause a random weapon equipped by the target to have its durability altered by +x or -x. If it reaches 0 or lower, the weapon will break.

使用技能或者物品可以增加或者减少随机目标武器的耐久度x，如果到达0，则武器破损

	<Target Armor Durability: +x>
	<Target Armor Durability: -x>
Each hit of this skill/item will cause the target’s armor(s) durability to be altered by +x or -x. Depending on the ‘Damage All’ plugin parameter, this will affect either all armors or affect a random armor piece. If the item reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少目标装备的耐久度x，如果到达0，则装备破损

	<Target All Armor Durability: +x>
	<Target All Armor Durability: -x>
Each hit of this skill/item will cause all of the target’s armor(s) durability to be altered by +x or -x. If it reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少所有目标装备的耐久度x，如果到达0，则装备破损

	<Target Random Armor Durability: +x>
	<Target Random Armor Durability: -x>
Each hit of this skill/item will cause a random armor equipped by the target to have its durability altered by +x or -x. If it reaches 0 or lower, the armor will break.

使用技能或者物品可以增加或者减少随机目标装备的耐久度x，如果到达0，则装备破损

***
###Plugin Commands
***

There are a few plugin commands you can utilize to show/hide the Repair option in the Item Action Window and/or enable/disable it.

下面的插件命令可以让你开启修复耐久度选项

####Plugin Commands

	ShowRepairDurability
	HideRepairDurability
– This will show/hide the Repair command in the Item Action Window.

显示和隐藏修复耐久度菜单

	EnableRepairDurability
	DisableRepairDurability
– This will enable/disable the Repair command in the Item Action Window.

开启和关闭修复耐久度菜单

***

###Happy RPG Making!

