##YEP.98 – Common Event Menu
***
###Introduction
***

The Common Event Menu allows you to create your own custom menu setups. When using it, you can list whatever common events you so wish and generate a menu that when selecting the menu command, it will run the common event. This common event menu setup allows you to utilize a help window, a picture window, and a subtext window to allow for your own personal touch when using the common event window.

公共事件菜单允许制作自定义菜单设置，当你使用它时，你可以选择你希望执行的公共事件列表产生一个菜单。这个公共事件菜单允许你显示帮助信息，图片和下标文本。

***
###Instructions
***

The common event menu is constructed purely by plugin commands. You’ll have to carefully construct each plugin command to make the common event list appear the way you want. The following is an example of how to set up a common event menu with the default window layout:

这个公共事件菜单可以通过插件命令制作。你可以创建不同的菜单列表。下面是一些例子。

	SetCommonEventMenuSettings Default Setup
	ClearCommonEventMenu
	AddCommonEventMenu 1 2 3 4 5
	SetCommonEventMenuCancel 0
	OpenCommonEventMenu

To find out more details about how to set up the common event menus, be sure to read through the help file carefully!

如果你想知道更多设置细节，请详细阅读帮助文件

***
###Comment Tags
***

Common Events in RPG Maker MV do not have their own notetags. So to make up for that, we’ll be using comments instead. Simply create a comment event within the common event that will be used inside of the menu and use any of these comment tags:

MV中公共事件并没有他们的标签栏，所以我们使用事件中的注释命令。你可以使用下面的语句来简便的创建菜单

####Common Event Comment Tags:

	<Menu Name: x>
– This changes the appearance of the common event’s text when displayed in the common event menu list. If this tag isn’t used, the text displayed will be the common event’s name. You can use text codes.

菜单名字，如果没有设置，则显示公共事件名字

	<Icon: x>
– This changes the icon of the common event to x. If this tag isn’t used, the icon used will be the one set in the plugin’s parameters.

菜单图标，如果没有设置，则显示插件参数里的值

	<Picture: x>
– This sets a picture to be associated with this common event when it is highlighted. If this isn’t used, no picture will be displayed and it will be left empty.

菜单图片，如果没有设置，则不会显示

	<Help Description>
	text
	text
	</Help Description>
– This sets the help description used for the common event when it is selected in the common even menu list. If this tag isn’t used, the text displayed will be the default text from the plugin’s parameters.

设置帮助文本框，如果没有设置，则显示插件参数里的值

	<Subtext>
	text
	text
	</Subtext>
– This sets the subtext used for the common event menu’s subtext window while this common event is selected in the common event menu list. If this text isn’t used, the text displayed will be the default text from the plugin’s parameters.

设置帮助下标文本，如果没有设置，则显示插件参数里的值

***
###Lunatic Mode – Enabling/Disabling Common Events
***

For those with JavaScript experience, you can use the following comment tags for your common events to be enabled or disabled:

如果你有JavaScript经验，可以使用下面的标签

####Common Event Comment Tags:

	<Menu Enable Eval>
	if ($gameSwitches.value(10)) {
	enabled = true;
	} else {
	enabled = false;
	}
	</Menu Enable Eval>
– The ‘enabled’ variable determines if the common event can be selected or not. In the example above, Switch 10 needs to be ON in order for this common event to be selected.

开关10打开，菜单才可以选择

***
###Lunatic Mode – Showing/Hiding Common Events
***

For those with JavaScript experience, you can use the following comment tags for your common events to be shown or hidden:

如果你有JavaScript经验，可以使用下面的标签

####Common Event Comment Tags:

	<Menu Visible Eval>
	if ($gameSwitches.value(20)) {
	visible = true;
	} else {
	visible = false;
	}
	</Menu Visible Eval>
– The ‘visible’ variable determines if the common event is shown or hidden in the common event menu list. In the example above, Switch 20 needs to be ON in order for this common event to be visible and shown.

开关20打开，菜单才可以显示

***
###Plugin Commands
***

The following plugin commands are used to work the Common Event Menu. Look over each of the settings carefully:

你可以使用下面的插件命令

####Plugin Command:

—

ClearCommonEventMenu
– This clears all the listed common events from the Common Event Menu Data pool meaning it has to be filled again. You can do so with the next plugin command:

清除公共事件菜单所有的事件

—

	AddCommonEventMenu 1
	AddCommonEventMenu 2, 3, 4, 5
	AddCommonEventMenu 6 through 10
– This will add the listed common event numbers into the common event list that will be shown in the common event menu.

添加公共事件

—

	SetCommonEventMenuCancel 20
– This will set the cancel button for the common event menu to run common event 20 when canceled. If it is left at 0, no event will run, but the menu can allow the cancel button to be pressed (and prematurely end it).

设置取消按钮执行的公共事件

—

	DisableCommonEventMenuCancel
– This will disable the cancel button for the common event menu from being pressed. Pressing cancel while the common event menu is active will do nothing. Use ‘SetCommonEventMenuCancel x’ to re-enable the cancel button.

关闭取消按钮

—

	OpenCommonEventMenu
– After you’ve set everything up, this command will be used to open up the common event menu. This can be used on the map. If you are using the Battle Engine Core, this menu can be opened in battle as well. All of the common events listed by the ‘AddCommonEventMenu’ plugin command will appear in this list.

打开公共事件菜单。如果你使用了 Battle Engine Core，你可以在战斗中打开它。

—

	CommonEventMenuX 0
	CommonEventMenuY this.fittingHeight(2)
	CommonEventMenuWidth Graphics.boxWidth / 2
	CommonEventMenuHeight Graphics.boxHeight – this.fittingHeight(2)
	CommonEventMenuOpacity 255
	CommonEventMenuColumns 1
– These plugin commands allow you to adjust the x, y, width, height, opacity, and the number of columns used for the main common event menu list. Make sure all of these settings are done BEFORE the common event menu is opened with the ‘OpenCommonEventMenu’ plugin command.

这些插件命令可以调整菜单位置，宽高，透明度，列数。确保这些插件命令在OpenCommonEventMenu命令之前

—

	ShowCommonEventMenuHelp
	HideCommonEventMenuHelp
– This will allow you to decide if the help window will be shown or hidden for the next ‘OpenCommonEventMenu’ plugin command usage.

对于后面的打开菜单命令，隐藏菜单帮助窗口

—

	CommonEventMenuHelpX 0
	CommonEventMenuHelpY 0
	CommonEventMenuHelpWidth Graphics.boxWidth
	CommonEventMenuHelpHeight this.fittingHeight(2)
	CommonEventMenuHelpOpacity 255
– These plugin commands allow you to adjust the x, y, width, height, and opacity of the help window for the common event menu list. Make sure all of these settings are done BEFORE the common event menu is opened with the ‘OpenCommonEventMenu’ plugin command.

这些插件命令可以调整菜单帮助窗口位置，宽高，透明度。确保这些插件命令在OpenCommonEventMenu命令之前

—

	ShowCommonEventMenuPicture
	HideCommonEventMenuPicture
– This will allow you to decide if the help window will be shown or hidden for the next ‘OpenCommonEventMenu’ plugin command usage.

对于后面的打开菜单命令，隐藏菜单图片

—

	CommonEventMenuPictureX Graphics.boxWidth / 2
	CommonEventMenuPictureY this.fittingHeight(2)
	CommonEventMenuPictureWidth Graphics.boxWidth / 2
	CommonEventMenuPictureHeight this.fittingHeight(10)
	CommonEventMenuPictureOpacity 255
– These plugin commands allow you to adjust the x, y, width, height, and opacity of the picture window for the common event menu list. Make sure all of these settings are done BEFORE the common event menu is opened with the ‘OpenCommonEventMenu’ plugin command.

这些插件命令可以调整菜单图片位置，宽高，透明度。确保这些插件命令在OpenCommonEventMenu命令之前

—

	ShowCommonEventMenuSubtext
	HideCommonEventMenuSubtext
– This will allow you to decide if the help window will be shown or hidden for the next ‘OpenCommonEventMenu’ plugin command usage.

对于后面的打开菜单命令，隐藏菜单下标文本

—

	CommonEventMenuSubtextX Graphics.boxWidth / 2
	CommonEventMenuSubtextY Graphics.boxHeight – height
	CommonEventMenuSubtextWidth Graphics.boxWidth / 2
	CommonEventMenuSubtextHeight Graphics.boxHeight – this.fittingHeight(2) – this.fittingHeight(10)
	CommonEventMenuSubtextOpacity 255
– These plugin commands allow you to adjust the x, y, width, height, and opacity of the subtext window for the common event menu list. Make sure all of these settings are done BEFORE the common event menu is opened with the ‘OpenCommonEventMenu’ plugin command.

这些插件命令可以调整菜单下标文本位置，宽高，透明度。确保这些插件命令在OpenCommonEventMenu命令之前

—

	SetCommonEventMenuSettings Default Setup
	SetCommonEventMenuSettings Basic Setup
– This allows you to set the common event windows to position themselves to the default setup provided by the plugin parameters or a basic setup made of just the main list and a help window.

设置菜单为默认设置，或者对于列表和帮助的基本设置

***
###Happy RPG Making!

