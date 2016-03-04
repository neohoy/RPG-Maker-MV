##YEP.74 – Target Core
***
###Introduction
***

While this plugin works independent of YEP_BattleEngineCore.js, if you want to utilize extra effects, place this plugin beneath YEP_BattleEngineCore.js in the Plugin Manager list.

这个插件独立于YEP_BattleEngineCore.js，如果你想使用额外的效果，请放于YEP_BattleEngineCore.js下面

The Target Core plugin is made to expand upon the existing target scopes provided by RPG Maker MV. This plugin enables you to use more target scopes, with a larger variety of ways to select actors and enemies with bonus ways to select targets combined with the Row Formation plugin.

目标核心插件是用来拓展目标范围的。这个插件可以让你使用目标范围，可以结合编队插件一起使用

***
###Notetags
***
If you would like to utilize custom target scopes for your skills and items, you can use these notetags:

如果你想定义你技能或者物品的攻击范围，可以使用这些标签

####Skill and Item Notetags:

	<Repeat: x>
This determines the number of times an action is repeatedly used on each target. This can go beyond the default editor’s limit of 9.

重复x次

	<Target: Everybody>
This targets all alive opponent and friendly members with the user being the very last target.

目标所有人

	<Target: x Random Any>
This adds x random alive opponents and/or allies.

随机目标

	<Target: Target All Foes>
This targets a single foe and then adds all alive opponent members.

所有敌方

	<Target: Target x Random Foes>
This targets a single foe and then adds x random alive opponent members.

随机敌方

	<Target: x Random Foes>
This adds x random alive opponent members. This can go beyond the editor’s default limit of 4 randomf oes.

随机敌方

	<Target: All Allies But User>
This will target all friendly alive members except for the user.

除了使用者的其余队友

	<Target: Target All Allies>
This will target a single ally and then adds all alive friendly members.

所有队友

	<Target: Target x Random Allies>
This will target a single ally and then adds x random alive allies.

随机队友

	<Target: x Random Allies>
This adds x random alive allied members.

随机角色

	<Target: Everybody param Multiple Of x>
Replace ‘param’ with ‘level’, ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘hp’, ‘mp’, or ‘tp’. This will make the skill or item indiscriminately target any living battler on the battlefield whose parameter value is a multiple of x.
NOTE: If you are using ‘level’, make sure you have YEP_EnemyLevels.js.

符合特定状态的角色

	<Target: Allies param Multiple Of x>
Replace ‘param’ with ‘level’, ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘hp’, ‘mp’, or ‘tp’. This will make the skill or item target any living allied party member on the battlefield whose parameter value is a multiple of x.
NOTE: If you are using ‘level’, make sure you have YEP_EnemyLevels.js.

符合特定状态的队友

	<Target: Foes param Multiple Of x>
Replace ‘param’ with ‘level’, ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘hp’, ‘mp’, or ‘tp’. This will make the skill or item target any living enemy battler on the battlefield whose parameter value is a multiple of x.
NOTE: If you are using ‘level’, make sure you have YEP_EnemyLevels.js.

符合特定状态的敌方

— YEP_RowFormation.js and YEP_BattleEngineCore.js Required —

	<Target: Enemy Row>
This will target the enemy row equal to that of the currently selected target enemy. The entire row will be selected as a whole.

目标敌人排

	<Target: Enemy Row x>
This will target specifically the enemy row x for the enemy unit. The entire row will be selected as a whole.

目标敌人x排

	<Target: Front Enemy Row>
This will target the front-most enemy row with alive members. If there is a row without any alive members, this will target the next row with an alive member.

目标敌人前

	<Target: Back Enemy Row>
This will target the back-most enemy row with alive members. If there is a row without any alive members, this will target the next row with an alive member.

目标敌人后排

	<Target: Ally Row>
This will target the enemy row equal to that of the currently selected target enemy. The entire row will be selected as a whole.

队友排列

	<Target: Ally Row x>
This will target specifically the allied row x for the allied unit. The entire row will be selected as a whole.

队友x排

	<Target: Front Ally Row>
This will target the front-most ally row with alive members. If there is a row without any alive members, this will target the next row with an alive member.

队友前排

	<Target: Back Ally Row>
This will target the back-most ally row with alive members. If there is a row without any alive members, this will target the next row with an alive member.

队友后排

***
###Happy RPG Making!