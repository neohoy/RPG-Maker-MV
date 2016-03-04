##YEP.35 – Stop Map Movement
***
###Introduction

A feature that was removed from RPG Maker 2000 and RPG Maker 2003 was the Stop Event Movement event. This event prevented events from automatically moving by themselves, so they don’t intrude on cutscenes, catch up to the player during messages, etc.

有个来自RM2000和RM2003的功能，就是停止事件移动事件。这个事件组织事件的自动移动，可以让事件不会干扰到截图，对话时捕捉玩家等。

This plugin recreates that feature in the form of a plugin command for you to use with RPG Maker MV!

这个插件重塑了这些特点

***
###Plugin Commands
***

You can use the following plugin commands to produce the following effects:

你可以用下面的插件命令来设置

####Plugin Command

	StopEventMovement
Stops events from automatically moving by themselves. You can still move events through movement routes set by your active event.

停止事件事件自动移动，你仍然可以设置事件移动路线来让其移动

	AllowEventMovement
Allows events to move automatically by themselves again. If you have any of the plugin parameters disabling events from moving during either events or messages, this will not bypass it.

允许事件自动移动。如果你用插件参数关闭了事件移动，他们不会动

	StopPlayerMovement
Stops player from being able to move via input. You can still move the player through movement routes set by your active event.

停止玩家移动，你可以移动通过设置移动路径来使其移动

	AllowPlayerMovement
Allows player to move again via input.

允许玩家移动

***
###Happy RPG Making!

