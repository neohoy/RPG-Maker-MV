##YEP.37 – Status Menu Core

This plugin replaces the Status menu with a whole new layout. Including the function to display more information regarding the actor.

这个插件用完整的新层代替了原有的身份菜单。包括可以展示更多角色信息的功能

***
###Introduction
***

This plugin replaces the Status menu with a whole new layout. Including the function to display more information regarding the actor. You can change the order commands appear in game with the Command Order parameter.

这个插件用完整的新层代替了原有的身份菜单。包括可以展示更多角色信息的功能。你可以用命令参数改变命令显示顺序。

To add more commands, insert extension plugins under this plugin in the Plugin Manager. Then, it will appear automatically in the Command Order where you placed the ‘Custom’ string or elsewhere if you’ve placed the extension plugin’s keyword elsewhere.

为了添加更多的命令，在这个底下可以插入拓展插件。

***
###Instructions
***

You can add and remove commands from the Command Window by changing the ‘Command Order’ parameter. Here is a list of commands you may use:

你可以添加和移除命令，通过命令顺序参数，这里有一个列表：

General
– Displays the current current stats and EXP for the actor.
显示角色原始状态和经验

Parameters
– Displays a parameter gauge of the actor relative to other stats.
显示和状态有关的参数槽，例如攻击力，防御力等

Elements
– Displays the listed elements and their elemental rates.
显示角色基本属性类型

States
– Displays the listed states and their status infliction rates.
显示状态列表和状态概率

Attributes
– Displays the listed attributes and their rates.
显示属性标志

Custom
– If you have any custom status window items to display, they will appear here.
自定义显示

Cancel
– Adds a cancel command for leaving the Status Menu.
取消菜单

***
###Adding Icons to Elements and Attributes
***

You can use icons for elements and attributes by using text codes.

你可以使用文字代码来为基本介绍和属性使用图标

In the RPG Maker MV editor’s database, types tab, for the elements, name them as such:

在MV默认数据库里，在基本类型里，可以这么写

	\i[64]Fire

This will enable you to give the element an icon. You can also change the text color and such using any of the available text codes.

这将让你给基本部分一个图标。你可以改变文字颜色，或者使用可运行的文字代码

The same is applied for Attributes except you modify it within this plugin’s parameters. If you wish to display ‘HP Regen Rate’ with an icon, name it:

对于属性来说也是一样的，你也可以通过插件参数来设置。

	\i[72]HP Regen Rate

The icons will be drawn for the said attributes in addition to any other text code modifications used.

这个图标将会绘出属性

***
### Happy RPG Making!