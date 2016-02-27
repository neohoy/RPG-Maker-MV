##YEP.17 – Region Events
* 这个插件的功能很简单，可以用地图上的Region ID来调用某个公共事件。
* 下面的配置就不一一翻译了，从Region1到Region255代表了RegionID的256个图块
* 默认值default为0 代表该regionID没有绑定任何公共事件，如果你想绑定公共事件
* 就把0改为公共事件的编号
* 举个例子：我定义了一个公共事件0005,事件触发效果为屏幕闪烁、玩家队伍HP减少10%
* 我现在把region1的default值改为5，并在地图上所有沼泽区域覆盖region1图层
* 那么当角色进入所有沼泽地形时就会触发上述事件，实现地形伤害效果。
* 这种方法比修改伤害地形类型有效，在于事件可以触发更多连锁效果，比如闪屏、弹出对话框等

Apply common events to specified regions! Simply by stepping on a tile marked by that region will trigger a specific common event!

给特殊区域绑定公共事件。走到贴上公共事件的区域就会触发特殊事件

WARNING: Keep in mind that if you apply this in areas with step encounters, it will not cause the encounter countdown value to go down. This is how RPG Maker MV handles it. The same way if you were to lay out your map with touch-events that trigger common events, the encounter countdown value would not go down either. To get around this, within the common event used, place a script call with $gamePlayer.updateEncounterCount().

警告：如果你设置了遭遇模式，这不会降低步行遭遇数。这是MV软件检索的。类似如果你放置了触碰事件，步行遭遇数也不会降低。如果你在事件触发时改变，可以用上诉脚本命令
***
###Introduction and Instructions
***

There are 255 Regions you can mark on your map. You can set it so that when players step on those specific Regions, a Common Event will play each time they step on it. To do so, bind a Common Event’s ID to the Region number in this plugin’s parameters. It will make it so that any tile with that very specific Region ID to trigger an on-Player Touch event using the Common Event ID that you have marked for it.

地图上有255个区域可以标记。你可以通过插件绑定事件ID，来让玩家步行此区域触发。

Keep in mind that if any common event occurs during a touch input, it will clear the touch input as intended by the game engine.

注意如果任何事件通过触碰发动，这将会清除游戏触碰记录

***
###Notetags
***

You can use this notetag inside of your maps.

以下注释命令用在地图配置界面。

####Map Notetags:
	<Region x Event: y>
If the player steps onto a tile marked by Region x, it will run the common event y. This will override the default settings marked in the editor specifically for that map.

自定义region ID为X的图层块，会触发公共事件Y。注意X范围为1-255，Y的范围为你自定义公共事件的编号。

***
###Happy RPG Making!

