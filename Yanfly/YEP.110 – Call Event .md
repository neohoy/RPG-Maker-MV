##YEP.110 – Call Event – RPG Maker MV
***
###Introduction
***
This is a reproduced method from RPG Maker 2000 and RPG Maker 2003. It allows the game to call a page’s events as if it were a common event. These events can be drawn from any event on any map within the game.

这是来自RPG Maker 2000和 RPG Maker 2003的一个方法的重制。这允许去调用事件页内的事件。这些被调用的事件可以使任何地图上的任何事件
***
###Plugin Commands
***
To call upon events from the current map or a different map, use the plugin commands found below:

插件参数

####Plugin Commands:

	CallEvent x
– This will call upon event x from the current map and use the event list from the first page of the event.

调用初始地图事件

	CallEvent x, Page y
– This will call upon event x from the current map and use the event list from page y of the event.

调用初始地图事件的特点页

	CallEvent x, Map y
– This will call upon event x from map y and use the event list from the first page of the event.

调用指定地图的事件

	CallEvent x, Page y, Map z
– This will call upon event x from map z and use the event list from page y of the event.

调用指定地图的事件的特点页

	CallEvent x, Map y, Page z
– This will call upon event x from map y and use the event list from page z of the event.

调用指定地图的事件的特点页

Note1: Because of the programming structure of RPG Maker MV’s source, the called event data may or may not be instantaneous depending on the size of the map file that is needed to be loaded. At best, it will take a couple of frames of loading time depending on the size.

注意1：由于RPG Maker MV的运行结构的问题，调用事件也许不会立即执行，这取决于所需载入地图的大小，也许会花费几帧来载入

Note2: If any of the events, pages, and/or maps do not exist, then no events will be called and the plugin will skip forward as if nothing has happened. Be cautious about how you call these call events.

注意2：如果任何事件、事件页或者地图不存在，那么事件将不会被调用，插件将会忽略就像什么都没发生。因此要谨慎选取你要调用的事件

***
###Happy RPG Making!

