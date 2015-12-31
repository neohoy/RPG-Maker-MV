## YEP.8 – Skill Core 

The Skill Core plugin enables you to modify the core aspects of skills such as the cost and effects. With this plugin, HP costs are also implemented, too.

技能核心插件能够修改技能的核心部分，比如技能的使用消耗和效果。利用这个插件，靠消耗HP来释放技能也是可行的。

***
### Introduction
***

Skills in RPG’s consist of three main components: Costs, Damage, and Effects. Although not all components are required for a skill, they certainly make up a good chunk of it. Damage will be handled by another plugin, but this plugin will provide a core handling for skill costs and skill effects.

RPG中的技能由三个成分组成：消耗，伤害，以及特效。这三个成分确实是一个技能的重要组成部分，尽管未必同时存在。伤害是由另一个插件决定的，但这个插件将是技能消耗和技能特效的核心决定因素。

This plugin also includes the ability for battlers to swap their HP, MP, and/or TP gauges for something different if it would fit the character better (for example, some classes don’t use MP and/or TP).

这个插件也包括让战斗者将自己的HP、MP和/或TP数值与不同的属性交换，如果该属性更适合角色本身（例如，有些职业并不使用MP和/或TP）。

***
### Notetags
***

These notetags can adjust either skill costs or special skill effects.

这些注释可同时用于技能消耗或技能特效。

**Skill Notetags:**

技能的注释：

	<HP Cost: x>
	
> Changes the skill to have x as its HP cost. RPG Maker MV’s editor lacks HP cost functions so this would allow skills to use HP as their cost.

> 将技能的消耗增加x点HP。RMMV的制作人员没有设置以HP为技能消耗的功能，因此这个注释起到了相应的作用。

	<HP Cost: x%>
> Changes the skill to cost a percentage of the character’s MaxHP value.

> 将技能的消耗增加最大HP值的x%。

	<MP Cost: x>
> Changes the skill to have x as its MP cost. This helps bypass the database’s hard limit of 9999.

> 将技能的消耗增加x点MP。它可以用来突破数据库的上限9999。

	<MP Cost: x%>
> Changes the skill to cost a percentage of the character’s MaxMP value.

> 将技能的消耗增加最大MP值的x%。

	<TP Cost: x>
> Changes the skill to have x as its TP cost. This helps bypass the database’s hard limit of 99.

> 将技能的消耗增加x点TP。它可以用来突破数据库的上限99。

	<TP Cost: x%>
> Changes the skill to cost a percentage of the character’s MaxTP value. Although the default MaxTP is 100, this tag will be useful for any plugins that will alter a character’s MaxTP values.

> 将技能的消耗增加最大TP值的x%。此注释适用于任一改变角色最大TP值的插件，尽管默认的最大TP是100。

	<Hide in Battle>
> This will hide and disable the skill during battle.

> 在战斗中隐藏此技能并使之不能使用。

	<Hide in Field>
> This will hide and disable the skill outside of battle.

> 在战斗外隐藏此技能并使之不能使用。

	<Hide if Learned Skill: x>
	<Hide if Learned Skill: x, x, x>
	<Hide if Learned Skill: x to y>
> Will hide and disable this skill if skill x has been learned. If multiple skills are listed, the skill will be hidden and disabled if any one of the listed skills have been learned.

> 如果技能x已被习得，将隐藏此技能并使之不能使用。若列出了多个技能，那么当任一列出的技能被习得时，注释的技能将被隐藏并不能被使用。

***
### Gauge Swapping
***

数值类型转换

This plugin also lets you swap around the HP, MP, and TP Gauges to any order you want assuming that all the plugins you use will keep the same order of HP, MP, and TP and does not override the default gauge drawing process. If you use any plugin extensions, they can be swaped in as well.

假设你使用的所有插件均保持HP、MP、TP这个顺序，并且不会推翻默认的数值运算进程，那么这个插件也能让你将HP、MP和TP数值类型重新排列为你想要的顺序。如果你使用任何扩展插件，它们也同样会被重排。

Note: If you do not have ‘Display TP in Battle’ checked under the System tab in the database, nothing will be shown for the third slot.

请注意：如果数据库中系统页下的“在战斗中显示TP”一项没有被选择，那么第三个位置的数值类型将不被显示。

**Class Notetag:**

职业的注释：

	<Swap Gauge x: y>
> This will change gauge x (1, 2, or 3) to y. Replace y with ‘HP’, ‘MP’, or ‘TP’ to have it display that gauge type in that gauge slot. If you wish for that slot to display nothing, insert ‘Nothing’ or ‘Null’ in place of y in the notetag.

> 把数据类型x（1,2或3）改为y。将y替换为“HP”,“MP”或“TP”来把它显示在相应的数据类型位置上。如果你想要在相应位置上什么都不显示，就在注释中y的位置输入“Nothing”或“Null”。

**Weapon, Armor, and State Notetags:**

武器、防具和特殊状态的注释：

	<Swap Gauge x: y>
> Actors with equipment or states that contain these notetags or enemies with states that contain these notetags will display those swapped gauges in place of the default settings or settings defined by the Class or Enemy notetags.

> 装备了写有此注释的装备的角色、和拥有写有此注释的状态的角色或敌人将显示被置换过的数值类型……。

> Priority will go in the following order: Weapons, Armors, States, Class, Enemy

> 其中优先级是按下列顺序排列的：武器，防具，特殊状态，职业，敌人。


***
### Lunatic Mode – Skill Costs
***

“疯狂模式”——技能消耗

For users who want more control over skill costs and skill effects, there exists notetags that allow you to apply code to the costs and/or effects of a skill. For effects, this will also extend towards item control, as well.

如果你想更好地控制技能消耗和技能特效，这里有包含能够针对技能的消耗和/或特效的代码的注释。其中的特效也可以延伸到对物品的控制。

	<Custom HP Cost>
	code
	code
	</Custom HP Cost>
> This allows the skill to have a custom HP cost based off of code. For the piece of code, ‘cost’ is a variable already predefined with the HP Cost and the HP percentage cost.

> 允许技能有一个不基于代码的自定义HP消耗。对于代码部分，“消耗”是一个已经预先由HP消耗和百分比HP消耗定义过的变量。

	<Custom MP Cost>
	code
	code
	</Custom MP Cost>
> This allows the skill to have a custom MP cost based off of code. For the piece of code, ‘cost’ is a variable already predefined with the MP Cost and the MP percentage cost.

> 允许技能有一个不基于代码的自定义MP消耗。对于代码部分，“消耗”是一个已经预先由MP消耗和百分比MP消耗定义过的变量。

	<Custom TP Cost>
	code
	code
	</Custom TP Cost>
> This allows the skill to have a custom TP cost based off of code. For the piece of code, ‘cost’ is a variable already predefined with the TP Cost and the TP percentage cost.

> 允许技能有一个不基于代码的自定义TP消耗。对于代码部分，“消耗”是一个已经预先由TP消耗和百分比TP消耗定义过的变量。

***
### Lunatic Mode – Custom Show Requirements
***

“疯狂模式”——自定义显示需求

For those who would like to show certain skills and disable them under any custom conditions using their JavaScript knowledge, use the following:

如果想要显示特定技能以及使它们在特定条件下不可使用（利用JavaScript的知识），使用下述代码：

	Skill Notetag:
	<Custom Show Eval>
	if (user.level > 50) {
	visible = true;
	} else {
	visible = false;
	}
	</Custom Show Eval>
> If the visible is set to true, the skill is shown (not hidden) and enabled if all other conditions are met. If visible is set to false, the skill is disabled and hidden from the list.

> 若“visible”设为“true”，那么技能就被显示（不被隐藏）而且是可用的，只要其它条件也满足。若“visible”设为“false”，那么技能就不可使用，并且从列表中被隐藏。

***
### Lunatic Mode – Custom Requirements and Execution
***

“疯狂模式”——自定义需求和执行

For those with a bit of JavaScript experience, you can use the following notetags to restrict a skill and what kind of code to process when executing the said skill.

如果你只有很少的JavaScript的使用经验，可以用下面的注释来限制一个技能以及执行技能时使用的代码类型。

**Skill Notetags:**

	<Custom Requirement>
	if ($gameParty.gold() > 1000) {
	value = true;
	} else {
	value = false;
	}
	</Custom Requirement>
> If value is set to true, the skill will be useable provided that all other requirements have been met. If the value is set to false, the skill won’t be useable.

> 若“value”设为“true”，技能就可以被使用，只要其它的条件也满足。若“value”设为“false”，技能将不可被使用。

	<Custom Execution>
	$gameParty.loseGold(1000);
	</Custom Execution>
> This runs the code between the notetags upon using the skill.

> 使用此技能时，这一条将在注释之间运行。

***
### Lunatic Mode – Custom Cost Display
***

“疯狂模式”——自定义消耗显示

For those with a bit of JavaScript experience, you can add new ways to display the skill cost.

如果你只有很少的JavaScript的使用经验，可以增加新的方式来显示技能消耗。

**Skill Notetags:**

技能的注释：

	<Cost Display Eval>
	var variableId = 1;
	var value = 1000;
	$gameVariables.setValue(variableId, value);
	</Cost Display Eval>
> This notetag runs an eval before displaying the skill’s cost. This is so you can set up variables and whatnot for your skill cost display text.

> 在显示技能消耗之前重新运算求出参数。这样你可以为你的技能消耗显示文本设置变量等。

	<Custom Cost Display>
	\c[4]\v[1]\c[0] Gold
	</Custom Cost Display>
> This is the custom text displayed before the rest of the skill costs. You can use text codes with this notetag.

> 这是在其它技能消耗前面显示的自定义文本。你可以通过这条注释来使用文本代码。

***
### Lunatic Mode – The Skill Phases
***

“疯狂模式”——技能阶段

For this skill, multiple effects are applied and at different phases. The various phases are as follows:

对于技能，在不同的阶段应用多个特效。可以变化的阶段如下：

Before Effect Phase (influenced by this plugin)
 if skill successfully lands:
– Pre-Damage Effect Phase (influenced by this plugin)
– Damage Phase
– Post-Damage Effect Phase (influenced by this plugin)
– Item Trait Effects Phase
After Effect Phase (influenced by this plugin)

特效阶段（被插件影响）之前
如果技能成功land：
 - 提前伤害效果阶段（被插件影响）
 - 伤害阶段
 - 后续伤害效果阶段（被插件影响）
 - 物品特性效果阶段
特效阶段（被插件影响）之后

There’s four phases which can be influenced by this plugin. Two of which do not matter if the effect successfully lands or not, two of which do matter if the skill does land.

这里有四个可被插件影响的阶段。其中两个与特效是否land无关，另外两个只当技能land才起作用。

**Skill and Item Notetags:**

技能和物品注释：

	<Before Eval>
	code
	code
	</Before Eval>

	<Pre-Damage Eval>
	code
	code
	</Pre-Damage Eval>

	<Post-Damage Eval>
	code
	code
	</Post-Damage Eval>

	<After Eval>
	code
	code
	</After Eval>

> If you wish to use custom effects for your skill, you can insert the respective notetags into the skill (or item) noteboxes and it will run the code that appears in between the tags. However, using any form of comments in this tag will block out code that follows.

> 如果你想对技能使用自定义特效，你可以在技能（或物品）的注释栏分别插入对应的注释，它运行注释之间出现的代码。然而，在注释中使用任一形式的comment会打断后面的代码。

***

### Happy RPG Making!