##YEP.52 – Region Battlebacks

* region战斗背景定义工具--可以使用区域图块组控制你遇敌时的战斗背景
* 什么叫区域图块组？就是图块组里的R选项卡,里面是1-255的ID标识
* 同时这个插件还可以让你修改默认地形的遇敌背景,很方便。
* --翻译 by 抖M俱乐部的 SmithJiong/bennett01/SOAP
* 转载请注明出处
* 注意：下面parameters配置中,Battleback1表示背景图下层，即img\battlebacks1中的文件
* Battleback2表示背景图上层，即img\battlebacks2中的文件，不再单独解释。
* paremeters配置主要让你修改默认地图战斗背景使用，
* 如果你想使用region区块标记不同的战斗背景,请使用地图配置界面的注释命令。

***
###Introduction
***

When using an overworld map, you actually have no control over any of the battlebacks used for the region you’re in. Although they sometimes make sense if you’re using the default RTP graphics, other parts of the terrain do not translate well if you’re using custom graphics with different names. As a result, this can result in certain images not loading and promptly crashing the game.

使用世界地图时，你会发现自己并不能使用region区块来控制战斗背景。当然，本插件还能有效避免因为其他地图上战斗背景名称不匹配和加载失败引起的游戏崩溃。

This plugin will allow you to alter the battlebacks used by default for the overworld in addition to bind specific battlebacks to specific tiles on the map through usage of regions.

本插件可以允许你改变默认地形的默认战斗背景，同时也可以让你用地图注释命令定义使用region区块定义的特别战斗背景

***
###Notetags
***

To bind specific battlebacks to certain region ID’s, you can use these following notetags:

要绑定背景地图给特殊的region区块，你可以使用下面的的注释命令:

####Map Notetags:

	<Region x Battleback1: filename>
	<Region x Battleback2: filename>
This will change the battleback1 or battleback2 for region x to use the battleback image with the matching filename. When writing out the filename, it is case sensitive. Do not insert the file extension.

很简单x为region区块的ID号,filename为背景图片名称。注意这里只需要用文件名，不需要路径，你的所有战斗背景都应该放在游戏工程的原始目录下面。

For example:

If you want Region 5 to use battleback1 Dirt2.png and battleback2 as Forest.png, you would use these two notetags:

	<Region 5 Battleback1: Dirt2>
	<Region 5 Battleback2: Forest>

Insert these combinations into the noteboxes of the maps you wish to use specific battlebacks per region for.

上面的命令实现了如果玩家踏入地图上ID为5的region标记区域触发的战斗都将会使用以Dirt2文件为地、Forest文件为天的战斗背景。

***
###Happy RPG Making!

