##YEP.95 – Class Base Parameters
***
###Introduction
***

This plugin requires YEP_BaseParamControl. Make sure this plugin is located under YEP_BaseParamControl in the plugin list.

这个插件需要YEP_BaseParamControl，确保放在它下面

For those who don’t like the way base parameters are determined by the editor, you can use your own formulas to determine the parameter growth for each class using this plugin. This plugin also allows you to adjust the exp needed for each level per class.

你可以设置每个职业的的基础参数公式。你甚至可以调整每个职业的每个等级

***
###Lunatic Mode – Custom Class Parameters
***
If your formulas are short and simple, you can use this notetag to cover the entire formula list for all of the base parameters:

如果你的公式很简单，你可以使用这个标签来覆盖所有基础参数

####Class Notetag:

	<Custom Class Parameters>
	maxhp = level * 30 + 300;
	maxmp = level * 20 + 150;
	atk = level * 15 + 15;
	def = level * 11 + 16;
	mat = level * 12 + 14;
	mdf = level * 10 + 13;
	agi = level * 14 + 15;
	luk = level * 13 + 12;
	exp = level * 100;
	</Custom Class Parameters>
The ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, and ‘exp’. variables each refer to their own individual stats. The ‘level’ variable refers to the actor’s current level. The formula can be made any way you like as long as it returns a legal number.

更改相应参数即可

*Note: The ‘exp’ stat here refers to the amount of exp needed to reach the next level.

注意：exp这里指的是升级所需经验

***
###Lunatic Mode – Detailed Custom Parameter Formulas
***

For those who wish to put a bit more detail in calculating the formula for each stat, you can use the following notetag setup:

对于想调整更多细节的，你可以采用这个标签。

####Class Notetags:

	<Custom Param Formula>
	if (this.name() === ‘Harold’) {
	value = level * 30 + 300;
	} else {
	value = level * 25 + 250;
	}
	</Custom Param Formula>
Replace ‘Param’ with ‘maxhp’, ‘maxmp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, or ‘exp’. The ‘value’ variable is the final result that’s returned to count as the base class parameter. The ‘level’ variable refers to the actor’s current level. The formula can be made any way you like as long as it returns a legal number.

更改相应参数即可

*Note: The ‘exp’ stat here refers to the amount of exp needed to reach the next level.

注意：exp这里指的是升级所需经验

***
###Happy RPG Making!

