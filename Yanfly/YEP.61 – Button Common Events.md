##YEP.61 – Button Common Events

***
###Introduction
***

This plugin enables you to bind common events to the individual buttons on your keyboard. Instead of having the standard Z for OK and X for cancel, you can make other keys work differently. With the exception of important keys that shouldn’t be altered, nearly full access is given across the span of the keyboard.

这个插件能够让你把公共事件绑定在键盘按键上。除了标准的z对应确定，x对应取消，其他的可以更改。除了特殊的按键，几乎你可以更改为键盘上任何一个按键

***
###Instructions
***

In the plugin’s parameters, you will see a list of all the keys that you can bind to a common event. If that number is something other than 0, then the number associated with it will be the common event that will run. If you assign it to a common event ID that does not exist, you will get an error so please be wary of that.

在插件参数里，你可以看到你可以绑定事件的按键。

You may also notice that some of the keys have in parenthesis a word like (OK) or (Cancel) next to them. What this means is that those keys already have a function assigned to them by the game. If you assign a common event to these keys, the native function of the key will be removed in favor of the common event you’ve assigned.

你可以注意到有些按键已经标注有功能，如果你对这些按键绑定事件，则原有的功能会被移除

Here is a list of the keys that already have a common assigned:

这里是一个按键功能表

Key – What they’re assigned to

– Q – Assigned to PageUp
– W – Assigned to PageDown
– Shift – Assigned to Dash
– Z – Assigned to OK
– X – Assigned to Cancel
– Space – Assigned to OK
– Left – Assigned to moving left
– Up – Assigned to moving up
– Right – Assigned to moving right
– Down – Assigned to moving down
– Insert – Assigned to Cancel
– Page Up – Assigned to PageUp
– Page Down – Assigned to PageDown
– Numpad 0 – Assigned to Cancel
– Numpad 2 – Assigned to moving down
– Numpad 4 – Assigned to moving left
– Numpad 6 – Assigned to moving right
– Numpad 8 – Assigned to moving up

Once again, if you assign common events to these keys, the common event will removing the binding the key had natively. However, this will only apply while the player is in the field map. Being inside of a menu or battle system will restore the previously native functions.

在强调一下，如果你为这些按键设置了事件，原有的事件会被移除。但是仅限于地图，在菜单和战斗内则依旧执行原有的功能。

***
###Compatibility Issues
***

This plugin will most likely have compatibility issues with anything that alters keystrokes or makes use of them through a different manner.

这个插件和其他更改按键的插件有兼容性问题

This will include the KeyboardConfig.js that was provided for the RPG Maker MV plugin pack made by Yanfly Engine Plugins. A future revision of the KeyboardConfig.js will be made to accomodate the changes made by this plugin to give better control and access.

这其中包括为MV提供的KeyboardConfig.js。未来的版本，KeyboardConfig.js会依赖这个插件做出一些调整

***
###Plugin Commands
***

For those who would like for a way to toggle back and forth between the bound common events and the default buttons, use these plugin commands.

对于那些希望可以来回切换按键事件的人，可以使用下面的插件命令

####Plugin Commands

	RevertButton Ok
	RevertButton Cancel
	RevertButton Dash
	RevertButton PageUp
	RevertButton PageDown
	RevertButton Left
	RevertButton Up
	RevertButton Right
	RevertButton Down
	RevertButton All
– Reverts all keys bound to any of the original functions back to their original buttons and unbinds the common events bound to them. If the “All” function is reverted, then all affected buttons will revert back to their original functions.

将按键功能撤回原始功能

	SwitchButton Ok
	SwitchButton Cancel
	SwitchButton Dash
	SwitchButton PageUp
	SwitchButton PageDown
	SwitchButton Left
	SwitchButton Up
	SwitchButton Right
	SwitchButton Down
	SwitchButton All
– Switches all keys with original functions to use the common event binds instead of their original versions. If the “All” function is switched, then all affected buttons will switch to common event bindings if there are any.

开关事件绑定功能

	TriggerButton Ok
	TriggerButton Cancel
	TriggerButton Dash
	TriggerButton PageUp
	TriggerButton PageDown
	TriggerButton Left
	TriggerButton Up
	TriggerButton Right
	TriggerButton Down
– This will cause the game to simulate triggering the button command of one of those original functions even if there is a common event bound to all of the keys of that original function.

触发事件绑定功能

***
###Happy RPG Making!

