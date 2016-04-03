##YEP.87 – Map Select Skill
***
###Introduction
***

This plugin produces a window similar to that of the Select Item Window, but instead, it displays a list of skills from a designated actor and the skill type selected. When a skill is selected, it set the choosen variable’s value to become that of the picked skill’s ID.

这个插件提供了简便的窗口来选择技能，当你选择技能时，变量值将会变成技能ID

***
###Plugin Commands
***

Use the following plugin commands to utilize the Map Select Skill plugin.

— Plugin Commands —

	MapSelectSkill v a s
– This will open up the Map Select Skill window. Replace ‘v’ with the ID of the variable you wish to set to the selected skill. Replace ‘a’ with the ID of the actor whose skill list you want to see. ‘s’ is optional, but if used, it will display the skills from skill type ‘s’ only. Replace ‘s’ with the skill type’s ID number.

v是变量ID，a是玩家ID，s是技能类型

	MapSelectSkillColumns x
– Sets the number of columns for the Map Select Skill Window to x.

选择技能框的列数

	MapSelectSkillRows x
– Sets the number of rows for the Map Select Skill Window to x.

选择技能框的行数

	MapSelectSkillWidth x
– Sets the width for the Map Select Skill Window to x. If 0 is used, then the window width will be the screen width.

选择技能框的宽度

	MapSelectSkillX left
	MapSelectSkillX center
	MapSelectSkillX right
– Sets the Map Select Skill Window to be aligned to the left side of the screen, center of the screen, or right side of the screen.

选择技能框的横向位置

	MapSelectSkillY top
	MapSelectSkillY middle
	MapSelectSkillY bottom
– Sets the Map Select Skill Window to be aligned to the top of the screen, middle of the screen, or bottom of the screen.

选择技能框的竖向位置

	EnableAllMapSelectSkills
– This will cause all of the skills listed to become selectable regardless of whether or not the actor is able to use them at the time.

开启选择技能框的功能

	NormalAllMapSelectSkills
– This will cause all of the skills listed to be enabled or disabled based on whether or not the actor is able to use the skill at the time.

开启全部技能列表

	ShowMapSelectSkillCost
– Show the cost of the skills in the Map Select Skill Window.

显示技能消耗

	HideMapSelectSkillCost
– Hide the cost of the skills in the Map Select Skill Window.

隐藏技能消耗

***
###Happy RPG Making!