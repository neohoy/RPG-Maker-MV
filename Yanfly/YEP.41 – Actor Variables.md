##YEP.41 – Actor Variables

This plugin requires the Status Menu Core. Ever wanted to display unique Game Variables into the status menu to portray your actors? Now you can! These variables can come from a global or individual source per actor. Variables listed in the Global Columns found in the parameters will be listed for all actors. Variables defined in the actor noteboxes will be listed for that actor when displayed.

这个插件需要身份菜单核心插件。你想要展示特有的游戏变量进入你的角色身份菜单吗？现在你可以了！这些变量可以来自全局变量或者每个角色的独有变量。在参数内找到的全局变量都可以被列举。角色备注框里里设置的变量将会展示在角色栏

***
###Introduction
***

This plugin requires YEP_StatusMenuCore.js.
Place this plugin under YEP_StatusMenuCore.js in the Plugin Manager.

这个插件需要YEP_StatusMenuCore，确保它放在YEP_StatusMenuCore下面

This plugin lets you place variables into the Status Menu Core in a unique page for display as actor data. These variables can come from a global or individual source per actor. Variables listed in the Global Columns found in the parameters will be listed for all actors. Variables defined in the actor noteboxes will be listed for that actor when displayed.

插件让你能够把变量放入身份菜单的特殊页显示出来。这些变量可以来自全局变量或者每个角色的独有变量。在参数内找到的全局变量都可以被列举。角色备注框里里设置的变量将会展示在角色栏

If you wish to place the Actor Variables tab in the Status Menu in a specific spot, place ‘Variables’ without the quotes in the Status Menu Core’s Command Order parameter. If it’s not present there, it will automatically order itself in the ‘Custom’ tab.

如果你想把角色变量栏放入身份菜单，请把‘Variables’ 放入身份菜单核心插件命令参数栏，否则，将会出现在‘Custom’栏

***
###Notetags
***

Use the following notetags to display variables in your Status Menu.

使用下面的标签可以显示变量

####Actor Notetags:
	<Column x Variables: y>
	<Column x Variables: y, y, y>
	<Column x Variables: y to z>
This will display in column x (1 through 4) the variable(s) y. If using the y to z notetag, this will display all the variables from y to z.

这将在x行显示变量y。如果你使用了y到z，则会显示y到z的所有变量

***
###Variable Icons and Display
***

To display icons and change the display of your variables, write the name of your variables like text codes in the variable editor.

如果想要显示图标和改变显示的变量，你可以想文本代码一样写下命令

A variable name like this \i[42]Variable Name will show up with an icon.

这段命令将会显示一个图标

However, if you wish to make notes that do not appear, you can place the notes between << and >>. 

如果你想隐藏名字，你可以用《》来设置

For example:

Hello <<You can’t see me>>World!

will show up as ‘Hello World!’ because of the << and >> markers.

例如这段代码，将会显示‘Hello World!’。《》内的不会显示

***
###Happy RPG Making!

