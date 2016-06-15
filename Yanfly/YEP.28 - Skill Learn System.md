## YEP.28 – Skill Learn System

This plugin enables your game's actors to learn skills from the skill menu. This can be done via either gold, items, or Job Points. It provides the player an alternate way of acquiring skills aside from leveling up.

此插件可以让游戏中的角色在技能菜单中学习技能。学习技能的代价可以是金钱、物品或所谓的“职业点数”（Job Point）。它能够提供除了升级以外的获得技能的可选方式。

**Add Ons**  
Fox's JP Levels – This Plugin adds levels to the Yanfly's JobPoint System, like Final Fantasy Tactics had. It allows for restrictions on what skills your allowed to buy with the SkillLearnSystem based on the current classes' Job Level. It allows for restrictions on what class your allowed to equip with the ClassChangeCore based on the current classes' Job Level. The Job automatically gains levels just by gaining JobPoints.

Fox的JP（职业点数）等级——这个插件向Yanfly的JP系统中添加了等级概念，就像《最终幻想战略版》中那样。根据你当前职业的“职业等级”（Job Level），你可以在SkillLearnSystem中获取相应的技能，也可以在ClassChangeCore中更换相应的职业。而职业等级只是通过增加JP来提高的。
地址http://forums.rpgmakerweb.com/index.php?/topic/51837-jp-levels/

***
### Introduction
***

This plugin enables your game's actors to learn skills from the skill menu. This can be done via either gold, items, or Job Points. It provides the player an alternate way of acquiring skills aside from leveling up.

此插件可以让游戏中的角色在技能菜单中学习技能。学习技能的代价可以是金钱、物品或所谓的“职业点数”（Job Point）。它能够提供除了升级以外的获得技能的可选方式。

This plugin can be used with YEP_JobPoints.js.

此插件可以通过YEP_JobPoints.js使用。

It is recommended to place this plugin under the YEP_JobPoints.js plugin in the Plugin Manager.

在插件管理页面中，我们建议把这个插件放在YEP_JobPoints.js的下面。

***
### Notetags
***
Use the following notetags to make use of the Skill Learn System.

通过下述注释来使用技能学习系统。

#### Class Notetag:

职业的注释：

	<Learn Skill: x>
	<Learn Skill: x, x, x>
	<Learn Skill: x to y>
Enables the class to be able to learn skill(s) x from the menu. Replace x with the skill's ID. If x to y is used, this enables the class to learn all the skills from x to y. Replace x and y with skill ID's.

让此职业能够在菜单中学习技能x。如果是第三种情形x to y，它允许职业学习从x到y的所有技能，其中x和y是技能的ID。

#### Skill Notetags:

技能注释：

	<Learn Cost: x Gold>
Sets the gold cost of learning this skill to x gold.

设置学习此技能所要花费的金钱为x。

	<Learn Cost: x JP>
Sets the JP cost of learning this skill to x JP. This note requires YEP_JobPoints.js in order to work.

设置学习此技能所要花费的JP为x。这一条需要YEP_JobPoints.js插件才能运行。

	<Learn Cost> 
	Item x: y 
	Weapon x: y 
	Armor x: y
	</Learn Cost>

or

	<Learn Cost>
	item name: y
	item name: y
	</Learn Cost>
Allows you to set the item, weapon, and armor costs of learning the skill. Replace x with the item's ID and y with the quantity of that item needed. If you decide to use the item name variant, replace the item name with the item's name as it appears in the database. If multiple items share the same name, the item with the highest ID will be used in the order of item, weapon, and then armor.  
*Note: If you are using YEP_ItemCore.js and Independent Items, the learn costs will not include independent items.

设置学习此技能所要花费的物品、武器和防具，其中x是物品的ID，y是所需物品的数量。如果你打算用物品的名称作为变量，那么把item name换为物品在数据库中的名称。但如果有多个物品的名称相同，那么将会使用ID最大的东西（按照“物品＞武器＞防具”的顺序）作为费用。
*注意：如果你在使用YEP_ItemCore.js插件及“独立物品”（Independent Items），那么学习费用将不包括那些独立物品。

	<Learn Require Level: x>
Causes the skill to require the actor's current level to be at least x before the skill even appears on the list to learn.

角色等级到达x之后，此技能才会出现在可学习技能的列表上。

	<Learn Require Skill: x>
	<Learn Require Skill: x, x, x>
	<Learn Require Skill: x to y>
In order for the skill to appear, the actor must know the other skill(s) of x. If x to y is used, the actor must know all the skills from x to y. Replace x and/or y with skill ID's.

角色必须已经掌握其他技能x，此技能才会出现（在列表上）。如果是第三种情形x to y，角色必须已经掌握从x到y的所有技能，其中x和/或y是技能的ID。

	<Learn Require Switch: x>
	<Learn Require Switch: x, x, x>
	<Learn Require Switch: x to y>
In order for the skill to appear, the switch(es) x must be on. If x to y is used, all of the switches from x to y must be on in order for the skill to appear. Replace x and/or y with switch ID's.

开关x必须已被打开，此技能才会出现。如果是第三种情形x to y，从x到y的所有开关必须已被打开，技能才会出现，其中x和/或y是开关的ID。

***
### Lunatic Mode – Custom Requirements and Costs
***
“疯狂模式”——自定义要求和花费


For those who understand a bit of JavaScript and wish to go further with customizing the process for the skill learning process, you can use the following notetags:

如果你只有很少的JavaScript使用经验，并且希望更好地定做技能学习的方法，那么你可以用下列注释：

#### Skill Notetags:

技能的注释：

	<Learn Show Eval>
	value = true;
	value = false;
	</Learn Show Eval>
For using a custom code to hide or show the skill, you can use these notetags. Returning value as true will cause the skill to appear regardless of all other requirements being unmet while returning value as false will cause the skill to appear regardless of all other requirements being met.

如果想用一串代码来隐藏或显示此技能，你可以使用这些注释。若返回value的值为true，那么即使其它要求不被满足，技能也会出现（在列表上）。而若返回value的值为false，那么即使其它要求被满足，技能也不会出现。

	<Learn Require Eval>
	value = true;
	value = false;
	</Learn Require Eval>
For those who wish to use their own custom requirements using code. This must return value as true in order for the skill to appear to be learnable. Avoid using comments that may potentially block out further code.

给希望通过代码设置自己特定的技能学习要求的人使用。只有返回value的值为true，技能才会显示为可学的。请避免使用可以停止后续代码工作的命令。

	<Learn Cost Eval>
	code
	code
	</Learn Cost Eval>
For those who know JavaScript, you can have custom actions be performed after the learning the skill through the learn skill menu.

如果你熟悉JavaScript，你可以在通过学习技能菜单学习技能之后自定义一些功能。

	<Learn Custom Text>
	text
	text
	</Learn Custom Text>
This will be the custom text shown underneath all the main costs. You can use text codes for this.

在主要花费的下面显示自定义文字。可以在这里使用文本代码。

***
#### Plugin Commands
***

插件命令

You can use the following Plugin Commands from the Event Editor to alter whether or not you want the ‘Learn Skill' command to appear in the skill scene or to have it enabled.

可以从事件编辑器（Event Editor）中使用下列插件命令，来确定你是否想让“学习技能”命令出现在技能界面以使之可行。

#### Plugin Command:

插件命令：

	ShowLearnSkill
Shows the ‘Learn Skill' command.

显示“学习技能”命令。

	HideLearnSkill
Hides the ‘Learn Skill' command.

隐藏“学习技能”命令。

	EnableLearnSkill
Enables the ‘Learn Skill' command.

使“学习技能”命令可行。

	DisableLearnSkill
Disables the ‘Learn Skill' command.

使“学习技能”命令不可行。

	OpenLearnSkill actor x
Opens Learn Skill menu for actor x.

为角色x打开学习技能菜单。

	OpenLearnSkill party x
Opens Learn Skill menu for party member x.

为队伍成员x打开学习技能菜单。

***

### Happy RPG Making!


 