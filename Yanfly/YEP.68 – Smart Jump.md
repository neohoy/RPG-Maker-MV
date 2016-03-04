##YEP.68 – Smart Jump

***
###Introduction
***

For those that may have made their own Jump system before with events, you may have come across the problem of being able to jump off the map, into places you’re not supposed to go, or even on top of events that shouldn’t be allowed to go on top of. This plugin helps faciliate eventing a Jump system for your RPG Maker game by introducing Smart Jumps.

对于那些想制作自己的跳跃系统的人，你也许遇到过跳进你不应该进入的区域或者位于某些事件之上，这个插件将会修复并提供一个智能跳跃系统

Smart Jumps will allow you to jump over areas, but will limit you from jumping on top of places you can’t go, on top of normal priority events, and set up boundaries (such as walls) that you normally cannot jump past.

智能跳跃允许你跳过区域，但是限制你跳在你不能去的地方。

NOTE: For users saying that Smart Jumps bypass On Touch Events and Poison Tiles, they do not. This is not a bug but rather the way events work. Depending on how long you set the wait time after a Smart Jump, it may bypass an ontouch event or not. I found the ideal wait time is 10 frames after a Smart Jump effect. You would encounter the same “problem” with events if you don’t time it right.


注意：对于使用者所说智能跳跃可以忽略接触事件和有毒地段，他们不可以。这不是BUG二更有可能是事件生效的方式。这取决于你设置智能跳跃后的等待时机，它可能会忽略接触事件。我发现如果你设置智能跳跃后的时间是10帧，它将会生效。

***
###Instructions – Setting Up Smart Jumps
***

Use the Plugin Command ‘SmartJump’ to make the player character perform a Smart Jump.

使用插件命令SmartJump来设置智能跳跃

Inside the plugin parameters, mark the Illegal Regions your player cannot jump past or on and then draw them on the map. Alternatively, you can mark certain tile types within the Database > Tileset tab and use Terrain Tags to restrict where the player cannot jump.

在插件参数里，标记不能跳跃的区域。你也可以在数据库里标记图块来限制玩家跳跃

***
###Notetags
***

You can use these notetags to set up what Terrain Tags that the player can’t jump on or past.

你可以使用下面的标签来设置玩家不能通过的区域

####Tileset Notetags:

	<Illegal Jump: x>
	<Illegal Jump: x, x, x>
	<Illegal Jump: x to y>
Replace x with the terrain tags you want to forbid the player from going past or landing on while doing Smart Jumps.

不能跳跃的区域

####Event Notetag:

	<Illegal Jump>
This will prevent the player from being able to jump on or over this event while doing Smart Jumps. If the event is set to Through mode, then the player can jump through or onto the event.

不能跳跃的事件

***
###Happy RPG Making!