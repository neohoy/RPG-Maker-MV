##YEP.18 – Region Restrictions

* 本插件可以使用Region图层阻挡事件或者玩家进入某些区域
* 注意：插件配置中定义的Region为全局生效，即在插件本身定义的region功能会适用于所有地图图层，如果你想在不同的地图定义不同的region阻挡功能，请参照下文的注释命令于各地图配置页面单独设置。

Don’t like having NPC’s wandering into places they don’t belong? Feel like the player shouldn’t have access to certain parts of the map? The Region Restrictions plugin lets you do just that by simply planting regions onto the map to prevent those nosy events from going to places they shouldn’t.

不喜欢NPC进入他们不属于的区域？

***
###Introduction and Instructions
***

Not everybody wants NPC’s to travel all over the place. With this plugin, you can set NPC’s to be unable to move pass tiles marked by a specified Region ID. Simply draw out the area you want to enclose NPC’s in on and they’ll be unable to move past it unless they have Through on. Likewise, there are regions that you can prevent the player from moving onto, too!

不是所有人都想让NPC能够随便溜达的！本插件可以让你你的NPC无法穿越某Region图层覆盖的区域。同样的，你也可以使用region图层设置总是允许玩家、NPC穿越的区域，从而忽略地形限制，如此就不必担心过多的具有跟随功能的NPC把你逼近死胡同、堵在大门口，而且能够使一些隐蔽通道、隐藏地区的设计更简单。

***
###Notetags
***

You can use this notetag inside of your maps.
以下注释命令用于地图属性界面

####Map Notetags:

	<Player Restrict Region: x>
	<Player Restrict Region: x, x, x>
	<Player Restrict Region: x to y>
Restricts region x for the player on this particular map. Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.
阻止玩家 通过ID为x的region图层，可以单独定义1个ID，也可以定义复数个，还可以定义区间。以下同理
  
	<Event Restrict Region: x>
	<Event Restrict Region: x, x, x>
	<Event Restrict Region: x to y>
Restricts region x for all events on this particular map. Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.

阻止事件 通过ID为x的region图层

	<All Restrict Region: x>
	<All Restrict Region: x, x, x>
	<All Restrict Region: x to y>
Restricts region x for the player and all events on this particular map.Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.

阻止事件和玩家 通过ID为x的region图层

	<Player Allow Region: x>
	<Player Allow Region: x, x, x>
	<Player Allow Region: x to y>
Allows region x for the player on this particular map. Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.

强制允许玩家 通过ID为x的region图层

	<Event Allow Region: x>
	<Event Allow Region: x, x, x>
	<Event Allow Region: x to y>
Allows region x for all events on this particular map. Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.

  强制允许事件 通过ID为x的region图层

	<All Allow Region: x>
	<All Allow Region: x, x, x>
	<All Allow Region: x to y>
Allows region x for the player and all events on this particular map.Use multiple x to mark more regions. From x to y, you can mark a multitude of regions.

  强制允许玩家和事件 通过ID为x的region图层

***
###Happy RPG Making!