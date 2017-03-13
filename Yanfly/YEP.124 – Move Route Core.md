##YEP.124 – Move Route Core – RPG Maker MV
###Introduction

RPG Maker MV gives us a lot of various commands to use for our Move Routes. However, it still imposes a lot of limitations on the system for what else could still be potentially useful for move route commands. This plugin will provide additional methods to construct move routes for your events and allow you to streamline the move route creation process.

MV提供了很多命令来设定移动路线。可是它仍然强制限定了很多有用的移动命令，这个插件将提供额外的方法来构建你自己的运动路线，并且可以制作运动路线的进程。

###Instructions – Simplified Movement Routes

If you want to make events move a certain way using the commands from this plugin, do the following:

如果你想使用这个插件来制作特定路线，你可以按照下面的步骤

1. Open the event you wish to move.
2. Make a Movement Route command or Automatic Custom Route.
3. Press “Script…”
4. Type in any of the desired following commands:

---

1. 打开你想移动的事件
2. 选择移动命令或者自定义移动
3. 选择 “Script…”
4. 输入下面的命令

---

<pre>

UP: x
LEFT: x
RIGHT: x
DOWN: x
UPPER LEFT: x
UPPER RIGHT: x
LOWER LEFT: x
LOWER RIGHT: x

This will make the designated event move the noted direction x amount of times. This is no different than inserting a direction multiple times with editor, but this is meant to serve as a way to consolidate commands.
Replace x with an integar value.
这个可以让事件按照指定方向前进指定步数，这个和系统直接插入没有却别，可以看做是传统命令的补充。
Example: Up: 10
Left: 7
Down: 3
Right: 4

</pre>
<pre>

ANIMATION: x

Play animation x on the designated event. Replace x with an integar value.
播放指定动画。
Example: Animation: 10

</pre>
<pre>

BALLOON: x
BALLOON: EXCLAMATION
BALLOON: !
BALLOON: QUESTION
BALLOON: ?
BALLOON: MUSIC NOTE
BALLOON: HEART
BALLOON: ANGER
BALLOON: SWEAT
BALLOON: COBWEB
BALLOON: SILENCE
BALLOON: …
BALLOON: LIGHT BULB
BALLOON: ZZZ
BALLOON: USER 1
BALLOON: USER 2
BALLOON: USER 3
BALLOON: USER 4
BALLOON: USER 5

Plays balloon ID x on the designated event.
Replace x with an integar value or replace it with one of the strings shown above to produce that specific balloon.
播放指定气泡图像
Example: Balloon: 5
Balloon: Heart

</pre>
<pre>

ICON BALLOON: x
ICON BALLOON: x to y

Requires YEP_IconBalloons.
This will make the designated event display an icon balloon using icon x or x to y if the latter is used.
Replace x and y with integar values.
需要YEP_IconBalloons插件支持，这个可以让气泡图像使用指定图标
Example: Turn Away: 20, 30

</pre>
<pre>

JUMP FORWARD: x

The designated event will jump in the direction it is facing x tiles.
Replace x an integar value.
事件将向面对方向跳跃
Example: Jump Forward: 5

</pre>
<pre>

JUMP TO: x, y
JUMP TO: EVENT x
JUMP TO: PLAYER

The designated event will jump to either the coordinates x, y, or event x on the map (if event x is present), or to the player’s location.
Replace x and y with integar values.
事件将会跳向指定坐标、事件x位置、角色所处位置等
Example: Jump To: 20, 30
Jump To: Event 5
Jump To: Player

</pre>
<pre>

MOVE TO: x, y
MOVE TO: EVENT x
MOVE TO: PLAYER

AVOID MOVE TO: x, y
AVOID MOVE TO: EVENT x
AVOID MOVE TO: PLAYER

CRASH MOVE TO: x, y
CRASH MOVE TO: EVENT x
CRASH MOVE TO: PLAYER

The designated event will move to either the coordinates x, y, or event x on the map (if event x is present), or to the player’s location. The designated event will determine what is the best route within 12 iterations to reach the marked location. The designated event will keep repeating this command until it has reached the coordinates.
Replace x and y with integar values.
事件将会自动移动到指定坐标、事件x位置、角色所处位置等，这些移动将会在12次迭代计算之内完成。在到达指定位置之前，事件会持续不断的进行路线计算。
‘Move To’ and ‘Avoid Move To’ will make the designated event move around the player and the player’s followers when calculating a path to move to.
‘Move To’ and ‘Avoid Move To’命令可以让系统计算玩家和跟随者
‘Crash Move To’ will allow collision with the player and/or followers.
‘Crash Move To’ 命令可以让玩家允许碰撞

Example: Move To: 20, 30
Move To: Event 5
Move To: Player
Avoid Move To: 30, 40
Crash Move To: 40, 50

</pre>
<pre>

PATTERN LOCK: x
PATTERN UNLOCK

For some reason, RPG Maker MV does not allow you to set the currently used pattern (sprite frame) within the Move Route editor. This command will allow you to do so. If Pattern Lock is used, the sprite will remain locked in that pattern position until unlocked.
Replace x an integar value.
出于某些原因，MV并不会让你理由路线编辑器来设置图像，这个命令可以让你实现。如果图像锁打开，图像将会锁定在位置上。
Example: Pattern Lock: 0
Pattern Lock: 2
Pattern Unlock

</pre>
<pre>

SELF SWITCH x: ON
SELF SWITCH x: OFF
SELF SWITCH x: TOGGLE

This will turn the self switch designed event (unless it’s the player) to either On, Off, or Toggle it On/Off.
Replace x with A, B, C, or D.
Those using YEP_SelfSwVar.js can use numbers, too.
可以操作事件的独立开关。如果你使用了YEP_SelfSwVar.js，则仍然可以继续使用数字。
Example: Self Switch A: On
Self Switch B: Off
Self Switch 123: Toggle

</pre>
<pre>

SELF VARIABLE x: y

Requires YEP_SelfSwVar.js. This will set the self variable x for the designated event (unless it’s the player) to y.
Replace x with an integar value.
Replace y with an integar value or code.
这个需要YEP_SelfSwVar.js支持，可以设置事件的独立变量
Example: Self Switch A: On
Self Switch B: Off
Self Switch 123: Toggle

</pre>
<pre>

STEP AWAY FROM: x, y
STEP AWAY FROM: EVENT x
STEP AWAY FROM: PLAYER

This will make the designated event step one tile away from map coordinates x, y, or event x on the map (if event x is present), or from the player’s current location.
Replace x and y with integar values.
可以让事件逃离指定坐标、指定事件、玩家当前位置等
Example: Step Away: 20, 30
Step Away: Event 5
Step Away: Player

</pre>
<pre>

STEP TOWARD: x, y
STEP TOWARD: EVENT x
STEP TOWARD: PLAYER

This will make the designated event step one tile toward map coordinates x, y, or event x on the map (if event x is present), or to the player’s current location.
Replace x and y with integar values.
可以让事件靠近指定坐标、指定事件、玩家当前位置等
Example: Step Toward: 20, 30
Step Toward: Event 5
Step Toward: Player

</pre>
<pre>

TELEPORT: x, y
TELEPORT: EVENT x
TELEPORT: PLAYER

This will instantly teleport the designated event to coordinates x, y, or event x on the map (if event x is present), or to the player’s current location on the map.
Replace x and y with integar values.
可以将事件立即传送到指定坐标、指定事件、玩家当前位置等
Example: Teleport: 20, 30
Teleport: Event 5
Teleport: Player

</pre>
<pre>

TURN AWAY FROM: x, y
TURN AWAY FROM: EVENT x
TURN AWAY FROM: PLAYER

This will make the designated event turn away from map coordinates x, y, or event x on the map (if event x is present), or from the player’s location.
Replace x and y with integar values.
可以让事件背向指定坐标、指定事件、玩家当前位置等
Example: Turn Away: 20, 30
Turn Away: Event 5
Turn Away: Player

</pre>
<pre>

TURN TOWARDS: x, y
TURN TOWARDS: EVENT x
TURN TOWARDS: PLAYER

This will make the designated event turn towards tile toward map coordinates x, y, or event x on the map (if event x is present), or to the player’s current location.
Replace x and y with integar values.
可以让事件转向指定坐标、指定事件、玩家当前位置等
Example: Turn Towards: 50, 60
Turn Towards: Event 5
Turn Towards: Player

</pre>

And that’s it for the specialized movement routes you can use.

这就是你可以使用的路线设定

###Notetags

These are some notetags you can utilize for your events.

你可以使用下面的备注来设定事件

####Event Notetags:

	<Always Update Movement>
– Most events don’t update unless they’re close to the screen. But any event with this notetag will always be updating regardless of whether they are close to the screen or not.

事件在关闭屏幕前一般不会刷新，这个可以让事件无论是否关闭屏幕都会刷新

###Lunatic Mode – Script Calls

For those with JavaScript experience and would like to use the raw command functions without resorting to the simplified commands, you can use the following code inside of a Script:

对于熟悉JavaScript的人，如果你想要使用原生命令而不是这些简单的替代命令，你可以使用下面的代码

	this.jumpForward(x)
– Replace x with the amount of tiles you want the designated event to jump forward. x will be automatically rounded to the nearest integar value if it is a float value.

	this.jumpToPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to jump towards. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.jumpToEvent(x)
– Replace x with the ID of the event you wish for the designated event to jump towards. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

	this.moveRepeat(direction, times)
– This will make the designated event move in ‘direction’ a certain amount of ‘times’. Replace ‘direction’ with the number value you wish the event to move in (refer to NumPad) and replace ‘times’ with the number of times to step in that direction.

	this.moveToPoint(x, y)
– This will calculate the best possible movement route for the designated event to reach coordinates x, y within 12 iterations. The designated event will keep repeating this command until it has reached the coordinates. This will cause the designated event to go around the player and followers on the map without colliding into them.

	this.moveToPoint(x, y, true)
– This will calculate the best possible movement route for the designated event to reach coordinates x, y within 12 iterations. The designated event will keep repeating this command until it has reached the coordinates. This will cause the designated event to crash into the player and/or any followers if they are in the path way.

	this.moveToEvent(x)
– This will calculate the best possible movement route for the designated event to reach event x within 12 iterations. The designated event will keep repeating this command until it has reached the coordinates. If 0 is used, it will refer to the player. This will cause the designated event to go around the player and followers on the map without colliding into them.

	this.moveToEvent(x, true)
– This will calculate the best possible movement route for the designated event to reach event x within 12 iterations. The designated event will keep repeating this command until it has reached the coordinates. If 0 is used, it will refer to the player. This will cause the designated event to crash into the player and/or any followers if they are in the path way.

	this.requestAnimation(x)
– Replace x with the animation ID you want to play on the designated event. x will be automatically rounded to the nearest integar value if it is a float value.

	this.requestBalloon(x)
– Replace x with the balloon ID you want to play on the designated event. x will be automatically rounded to the nearest integar value if it is a float value.

	this.stepAwayFromPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to step away from. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.stepAwayFromEvent(x)
– Replace x with the ID of the event you wish for the designated event to step away from. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

	this.stepTowardPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to step towards. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.stepTowardPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to step towards. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.stepTowardEvent(x)
– Replace x with the ID of the event you wish for the designated event to step towards. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

	this.teleportToPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to teleport to. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.teleportToEvent(x)
– Replace x with the ID of the event you wish for the designated event to teleport to. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

	this.turnAwayFromPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to turn away from. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.turnAwayFromEvent(x)
– Replace x with the ID of the event you wish for the designated event to turn away from. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

	this.turnTowardPoint(x, y)
– Replace x and y with the coordinates you wish for the designated event to turn towards. x and y will be automatically rounded to the nearest integar value if it is a float value.

	this.turnTowardEvent(x)
– Replace x with the ID of the event you wish for the designated event to turn towards. x will be automatically rounded to the nearest integar value if it is a float value. If 0 is used, it will refer to the player.

###Happy RPG Making!