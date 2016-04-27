##YEP.94 – Selection Control
***
###Introduction
***

This plugin requires YEP_BattleEngineCore and YEP_TargetCore. Make sure this plugin is located under both of those plugins in the plugin list.

这个插件需要YEP_BattleEngineCore和YEP_TargetCore。确保在这些插件下面。

When selecting targets, RPG Maker MV has it set by default that the list of valid targets is always either alive enemies, alive allies, or only dead allies. Actions would not be able to target either actors or enemies or change from single target to multiple targets. This extension plugin for the Target Core will allow you to break free of that restriction for better
selection control of targets as well as insert customized conditions.

当选择目标时，MV默认是从所有存活敌人，所有友军或者死亡友军中选择。然而有时候我们希望我们可以从特定的列表里面选择。这个目标核心插件的拓展插件可以让你自由的设置选择列表
***
###Notetags – General
***
To make skills and items select only certain types of battlers, you can use the following notetag setup to do so:

使用标签

####Skill and Item Notetags:

	<Single or Multiple Select>
This will allow the skill or item to be able to select either single targets or all targets at once. This will automatically make a skill default to single target selecting. You MUST change your scope in the database to work with this effect.

这将开启技能或者物品的单选或者多选能力

*Note: Having this option will cancel out AoE Circles and AoE Rectangles to avoid conflicting issues.

注意：这个选项将会取消技能范围释放来避免冲突

*Note: If there is an enemy with taunt, the option to switch between a group target and a single target will not be available.

注意：如果这里有敌人处于嘲讽状态，切换群组目标和单个目标的选项将不会生效

*Note: Enemy AI will NOT make use of the ability to toggle between single target and multi-target scopes.

注意：如果敌人的AI将不会在单个目标和多目标直接切换

	<Disperse Damage>
Used in conjunction with the above notetag, this will cause damage to be split evenly amongst the number of targets the skill is dispersed into. The damage dispersion effect will only occur if multiple targets are being selected after toggling.

产生伤害分散效果(此处待考证)

	<Enemy or Actor Select>
	<Actor or Enemy Select>
This will allow the player to toggle between selecting an enemy or actor for the action’s target scope. When using <Enemy or Actor Select>, it will first target enemies by default. Using <Actor or Enemy Select> will target actors by default. Using either notetag will change the action’s target scope to single target.
*Note: Enemy AI will NOT make use of the ability to toggle between actors or enemies for skill selection.

默认选择目标

*Note: If you use any <Select Condition> effects, all selection options provided by default with the plugin parameters will be reset under the assumption that it will no longer be an action of default nature. If this is the case, you will need to use the above notetags to specify how you wish to make your skill’s selection methods.

注意：如果你使用了<Select Condition>的命令，这个插件参数设置将被重置。

####Actor, Class, Enemy, Weapon, Armor, State Notetags:

	<Cannot Select: All>
All actions cannot select this battler unless it’s an action whose scope is a user scope.

此战斗者不可被选中

	<Cannot Select: Physical Hit>
	<Cannot Select: Magical Hit>
	<Cannot Select: Certain Hit>
This will prevent physical, magical, or certain hit actions from being able to select the battler. They will be excluded out of multi-hit skills, as well unless it’s an action whose scope targets the user itself. targets the user itself.

此战斗者不可被此类攻击选中

	<Cannot Select: Skills>
	<Cannot Select: Items>
This will prevent skills/items from being able to target the battler unless it’s an action whose scope targets the user itself.

此战斗者不可被技能或者物品选中

	<Cannot Select: Item x>
	<Cannot Select: Item name>
This will prevent item ‘x’ (or the named item) from being able to target the battler unless the item’s scope targets the user itself. If you have multiple items in your database with the same name, priority will be given to the item with the highest ID.

此战斗者不可被特定物品选中

	<Cannot Select: Skill x>
	<Cannot Select: Skill name>
This will prevent skill ‘x’ (or the named skill) from being able to target the battler unless the skill’s scope targets the user itself. If you have multiple skills in your database with the same name, priority will be given to the skill with the highest ID.

此战斗者不可被特定技能选中

	<Cannot Select: SType x>
	<Cannot Select: SType name>
This will prevent skills of skill type ‘x’ (or named) from being able to target the battler unless the skill’s scope targets the user itself. If you have multiple skill types in your database with the same name, then priority will be given to the skill type with the highest ID.

此战斗者不可被特定技能类型选中

	<Cannot Select: Element x>
	<Cannot Select: Element name>
This will prevent actions with an elemental ID of ‘x’ (or named) from being able to target the battler unless the action’s scope targets the user itself. If you have multiple elements in your database with the same name, then priority will be given to the element with the highest ID.

此战斗者不可被特定元素选中

***
###Notetags – Select Conditions
***

To impose specific conditions on which targets are valid targets, use the following notetag setup:

设置特殊情况

—

####Skill and Item Notetags:

	<Select Conditions>
	condition
	condition
	</Select Conditions>
Replace ‘condition’ with the desired condition setup. Insert multiple conditions to make an action require more conditions for viable targets. Using this will overwrite the default settings imposed by the plugin parameters so if you wish to use those settings, you’ll have to use the associated condition with it.

自定义设置语句。这将覆盖插件的默认设置
—

#####Conditions:

—

	Any Row
– Requires YEP_RowFormation.js. The battler can be targeted from any row it is in as a valid target. This will conflict with the other ‘Row Only’ select conditions.

需要配合YEP_RowFormation.js，战斗者可以被任何排选中

—

	Back Row Only
– Requires YEP_RowFormation.js. This will make only the back row battlers be selectable for target. The back row will refer to whatever row is in the back that has living members. If row 3’s enemies are all dead, but row 2 has living members, then row 2 will be considered the back row. This will conflict with the other ‘Row Only’ select conditions.

需要配合YEP_RowFormation.js，战斗者只能被后排选中，此处后排指存活战斗成员的最后一排

—

	Front Row Only
– Requires YEP_RowFormation.js. This will make only the front row battlers be selectable for target. The front row will refer to whatever row is in front that has living members. If row 1’s enemies are all dead, but row 2 has living members, then row 2 will be considered the front row. This will conflict with the other ‘Row Only’ select conditions.

需要配合YEP_RowFormation.js，战斗者只能被前排选中，此处前排指存活战斗成员的第一排


—

	Row x Only
– Requires YEP_RowFormation.js. This will make only battlers in row x be selectable for target. Any battlers not in row x will be excluded from target selection. This will conflict with the other ‘Row Only’ select conditions.

需要配合YEP_RowFormation.js，战斗者只能被特定排选中
—

	Row x Max
– Requires YEP_RowFormation.js. This will make all battlers who are located in a lower number row up to row x be selectable for target. Any battlers in a row number larger than x will be excluded from target selection.

需要配合YEP_RowFormation.js，战斗者只能被不超过某排选中

—

	Row x Min
– Requires YEP_RowFormation.js. This will make all battlers who are located in a row from row x onward selectable for target. Any battlers in a row number smaller than x will be excluded from target selection.

需要配合YEP_RowFormation.js，战斗者只能被不低于某排选中

—

#####Param stat eval
ie: 

	Param MaxHP >= 500
	Param HP% <= 0.30
	Param Level === 25
– This makes the selection have a check on the target’s parameter values before deciding if the target is a valid target for selection. You can replace ‘stat’ with ‘MaxHP’, ‘MaxMP’, ‘MaxTP’, ‘HP’, ‘MP’, ‘TP’, ‘HP%’, ‘MP%’, ‘TP%’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, ‘LUK’, or ‘LEVEL’. This run an eval check against that parameter owned by the target.

检查基础参数
—

	State: x
	State: name
– The target must have state ‘x’ in order to be selected as a valid target. If you’re using the named version of the condition and you have multiple states with the same name in your database, priority will be given to the state with the highest ID. If the target doesn’t have state ‘x’, then the target is not a valid target for selection.

检查状态

—

	Not State: x
	Not State: name
– The target must not have state ‘x’ in order to be selected as a valid target. If you’re using the named version of the condition and you have multiple states with the same name in your database, priority will be given to the state with the highest ID. If the target does have state ‘x’, then the target is not a valid target for selection.

检查是否不在状态

***
###Lunatic Mode – Custom Select Condition
***

For those with JavaScript experience, you can use the following notetags to make custom selection conditions for skills and items.

拓展模式

####Skill and Item Notetags:

	<Custom Select Condition>
	if (target.name() === ‘Harold’) {
	condition = true;
	} else {
	condition = false;
	}
	</Custom Select Condition>
The ‘condition’ variable determines if the condition will pass or not. If the variable returns ‘true’, the condition will pass. If the variable is ‘false’, the condition will fail and the target will not be a valid target for the action. Even if the <Custom Select Condition> notetag passes, all other selection conditions must pass, too.

例句

***
###Happy RPG Making!

