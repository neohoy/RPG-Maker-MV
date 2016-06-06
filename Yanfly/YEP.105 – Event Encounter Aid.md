##YEP.105 – Event Encounter Aid
***
###Introduction
***
For those who have on-screen encounters, you may have discovered that making touch encounters in RPG Maker MV to be rather difficult when it comes to performing a sneak attack upon an event or such. This plugin makes the event encounter checking process easier by providing six conditional script calls for you to utilize when checking event vs player positions.

对于想要设置明雷的玩家，你也许发现很难设置偷袭事件。这个插件通过不同情况的脚步很方便的事件和玩家所处位置
***
###Notetags
***
You can place these notetags into the notebox at the top of an event’s page. These notetags will enable unique effects for event encounters.

你可以把这些标签放在任何一个事件页顶部，这些事件将会开启事件遭遇的特殊效果

####Event Notetag:

	<Encounter Lock>
	<Encounter Direction Lock>
– This will cause the event to not immediately face the player when approached making it possible for the game to check the direction each is facing.

这将让事件不会马上面对玩家，而是检查面对方向

	<Follower Touch>
	<Follower Trigger>
– This will allow the event to trigger if the event touches a follower and not just the main player.

这将允许事件被跟随者触发

***
###Event – Conditional Branch – Script Calls
***
When using the Conditional Branch event, you can use these following in the ‘Script’ check category:

你可以使用下面的脚本

####Script Calls

	this.checkEventFacingPlayerFront()
– Returns true if the event is facing the player’s front.

事件在玩家前面

	this.checkEventFacingPlayerBack()
– Returns true if the event is facing the player’s back.

事件在玩家后面

	this.checkEventFacingPlayerSide()
– Returns true if the event is facing the player’s side.

事件在玩家侧面

	this.checkPlayerFacingEventFront()
– Returns true if the player is facing the event’s front.

玩家在事件前面

	this.checkPlayerFacingEventBack()
– Returns true if the player is facing the event’s back.

玩家在事件后面

	this.checkPlayerFacingEventSide()
– Returns true if the player is facing the event’s side.

玩家在事件侧面

Make sure these are spelled correctly. They are also case-sensitive. This means that even if you were to misspell or put a single letter in the wrong case, the effect will cease to work as this is code we’re dealing with.

请确保拼写正确，他们是很严格的语句。

***
###Happy RPG Making!
