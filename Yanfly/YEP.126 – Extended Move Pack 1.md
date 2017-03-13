##YEP.126 – Extended Move Pack 1 – RPG Maker MV
###Introduction

This plugin requires Move Route Core. Make sure this plugin is located under Move Route Core in the plugin list.

这个插件需要Move Route Core插件的支持，请置于Move Route Core下面

This plugin adds extra simplified move routes for your events with the main intention of creating specific behaviors in movement patterns. The patterns include the option to hug a side of the wall and move along that, moving a single direction until coming to a stop, relative opacity adjusting, and index shifting.

这个插件为移动系统添加了额外的移动路径方式，包括贴着墙面行走，直行遇到障碍物转弯，透明度调整，图像调整等。

###Instructions – Additional Simplified Movement Routes

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

HUG LEFT WALL
HUG RIGHT WALL

AVOID HUG LEFT WALL
AVOID HUG RIGHT WALL

CRASH HUG LEFT WALL
CRASH HUG RIGHT WALL

The designated event will move alongside the wall to its left/right. If there is no wall to its left/right side, it will turn that direction and move that direction if possible.
事件将会沿着墙边移动，如果没有墙面他会转个可以移动的方向
‘Avoid Hug Left Wall’ and ‘Avoid Hug Right Wall’ will make the event not collide with the player character and the player’s followers.
Avoid命令是禁止事件碰撞玩家
‘Crash Hug Left Wall’ and ‘Crash Hug Right Wall’ will allow collision with the player and/or followers.
Crash命令是允许事件碰撞玩家
Example: Hug Left Wall
Hug Right Wall
Avoid Hug Left Wall
Avoid Hug Right Wall
Crash Hug Left Wall
Crash Hug Right Wall

</pre>
<pre>

INDEX: x

Sets the designated event’s current character graphic index to x without needing to change its character graphic. Replace x with integar values between 0 and 7.
改变事件图像，索引值在0-7之间
Example: Index: 5

</pre>
<pre>

INDEX: +x
INDEX: -x

Adjusts the designated event’s current character graphic index by +x or -x without needing to change its character graphic as to move it a few stages. The index cannot go under 0 and cannot go over 7. Replace x with integar values between 0 and 7.
改变事件图像，索引值在0-7之间
Example: Index: +1
Index: -2

</pre>
<pre>

MOVE UP UNTIL STOP
MOVE LEFT UNTIL STOP
MOVE RIGHT UNTIL STOP
MOVE DOWN UNTIL STOP
MOVE UPPER LEFT UNTIL STOP
MOVE UPPER RIGHT UNTIL STOP
MOVE LOWER LEFT UNTIL STOP
MOVE LOWER RIGHT UNTIL STOP

AVOID MOVE UP UNTIL STOP
AVOID MOVE LEFT UNTIL STOP
AVOID MOVE RIGHT UNTIL STOP
AVOID MOVE DOWN UNTIL STOP
AVOID MOVE UPPER LEFT UNTIL STOP
AVOID MOVE UPPER RIGHT UNTIL STOP
AVOID MOVE LOWER LEFT UNTIL STOP
AVOID MOVE LOWER RIGHT UNTIL STOP

CRASH MOVE UP UNTIL STOP
CRASH MOVE LEFT UNTIL STOP
CRASH MOVE RIGHT UNTIL STOP
CRASH MOVE DOWN UNTIL STOP
CRASH MOVE UPPER LEFT UNTIL STOP
CRASH MOVE UPPER RIGHT UNTIL STOP
CRASH MOVE LOWER LEFT UNTIL STOP
CRASH MOVE LOWER RIGHT UNTIL STOP

MOVE FORWARD UNTIL STOP
AVOID MOVE FORWARD UNTIL STOP
CRASH MOVE FORWARD UNTIL STOP

The designated event will keep moving the noted direction until it it cannot pass in that direction anymore. Once that happens, it will move onto the next movement command in the move route list.
事件将会直行直到遇到障碍物，然后在执行下一段移动命令
The ‘Avoid’ versions of this command will make the event not collide with the player character and the player’s followers.
Avoid命令是禁止事件碰撞玩家
The ‘Crash’ versions of this command will allow collision with the player and/or followers.
Crash命令是允许事件碰撞玩家
Example: Move Right Until Stop
Avoid Move Left Until Stop
Crash Move Forward Until Stop

</pre>
<pre>

OPACITY: +x
OPACITY: -x

Adjusts the designated event’s opacity value by +x or -x instead of a set value like the editor’s opacity command. The opacity value will be added upon or subtracted upon the current opacity value. Replace x with integar values.
改变图像透明度
Example: Opacity: +50
Opacity: -30

</pre>
<pre>

OPACITY: +x%
OPACITY: -x%

Adjusts the designated event’s opacity value by +x% or -x% instead of a set value like the editor’s opacity command. The opacity value will be added upon or subtracted upon the current opacity value. Replace x with integar values.
改变图像透明度
Example: Opacity: +10%
Opacity: -20%

</pre>
<pre>

OPACITY: x%

Sets the designated event’s opacity value to x% instead of a set value like the editor’s opacity command. The opacity value will be automatically adjusted to meet the demands of the sprite. Replace x with integar values.
设置头像透明度
Example: Opacity: 50%

</pre>

###Happy RPG Making!