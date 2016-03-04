##YEP.19 – Save Event Locations
NPC’s often reset their map locations when a player reenters a map. However, you can change that using this plugin by having the game save their event locations!

当玩家重新载入一个地图时，NPC经常重置位置。现在你可以用这个插件来存储事件的位置

***
###Introduction
***

Normally in RPG Maker MV, leaving a map and returning to it will reset the map positions of all the events. For certain types of maps, such as puzzles, you would want the map to retain their locations.

通常在MV里，离开地图并重新进入，将会重置所以事件的位置。对于某些类型的地图，例如迷宫类，你希望可以存储他们的位置

***
###Notetags
***

####Map Notetag:
	<Save Event Locations>
This will cause the map to save every event’s location on that map. After leaving and returning to that map, the events will be reloaded onto their last saved positions in addition to the direction they were facing.

这可以存储事件位置。在重新载入地图后，事件将会进入他之前存储的位置

####Event Notetag:
	<Save Event Location>
This will enable this specific event to save its location on this map. After leaving and returning to the map, the event will be reloaded onto its last saved position in addition to the direction it was facing.

这可以存储特定事件的位置。在重新载入地图后，事件将会进入他之前存储的位置。

If you wish to reset the position of the Event, simply use the Event Editor and use “Set Event Location” to anchor the event’s location to the desired point as if you would normally.

如果你想重置事件位置，你可以用事件编辑器设置事件位置到指定即可。

***
###Plugin Commands
***

####Plugin Command

	ResetAllEventLocations
This resets all the event locations on the map.

重置地图上所有事件位置

***
###Happy RPG Making!