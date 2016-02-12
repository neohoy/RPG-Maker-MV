## YEP.20 – Event Chase Player

Events have a typically bland movement behavior. They either stand in one place, always chase you, always run from you, move randomly, or always just move in specified patterns. This plugin lets your events suddenly switch from their norm to chasing or fleeing from the player.

目前事件只拥有传统乏味的移动行为。他们站在一个地方，追寻你，远离你，随机移动，或者在一个设定路径行走。这个插件让你的事件可以迅速切换靠近角色和远离角色

***
### Introduction
***
This plugin allows you to make events that will chase the player or flee from the player when the player enters within range of the event or when the event sees the player.

在你靠近事件范围或者事件看到角色时，这个插件可以让你的事件追寻或者逃离角色。

***
### How to Use
***

Insert these lines into the script call window within the Movement Route event to give an event the chase or flee flag.

把下面这些脚本语句插入事件移动路线里，让其生效。

Note: This doesn’t work with players.

注意：这些对角色不生效。

#### Script Call lines

	this._chaseRange = x
	
Event will chase player if reaching x range.

如果角色距离事件x，事件追逐角色。

	this._fleeRange = x
	
Event will flea from player if reaching x range.

如果角色距离事件x，事件逃离角色。

	this._chaseSpeed = x
	
Event’s movement speed when chasing.

事件追逐速度

	this._fleeSpeed = x
	
Event’s movement speed when fleeing.

事件逃离速度

	this._sightLock = x
	
Event will flee/chase player for x frames.

事件追逐或者逃离角色时间

	this._seePlayer = true
	
Requires the event to be able to see player.

需要事件能够看到角色

	this._seePlayer = false
	
Doesn’t require event to be able to see player.

不需要事件能够看到角色

	this._alertBalloon = x
	
This balloon will play when player is seen.

当看到角色时弹出对白框

	this._alertSound = x
	
This sound will play when player is seen.

当看到角色时播放音乐

	this._alertCommonEvent = x
	
This event will play when player is seen.

当看到角色时执行公共事件

It is best to play this inside of a custom move route for the event at a high frequency rate. Keep in mind these effects only occur after the setting is made and ran, which means upon loading a map, if the event with a low frequency hasn’t loaded up ‘this._chaseRange = x’ in its movement queue yet, the event will not chase the player just yet.

这个最适合用来自定义移动路线的速度。记住这个效果需要事件被设置为移动，这意味着载入地图时，如果事件没有被载入命令，这个事件永远不会追逐角色。

***

### Happy RPG Making!


