##YEP.100 – Save Core
***
###Introduction
***
NOTE: THIS PLUGIN REQUIRES MV VERSION 1.1.0 OR HIGHER!

注意：这个插件只支持1.1.0以上的版本

This plugin provides a new save interface for the player. Along with a new interface, the player can also load and delete saves straight from the menu itself. This will in turn make the save command from the Main Menu always available, but the save option within the new save menu will be enabled depending on whether or not it is allowed or disallowed. From the interface, the player is given more information regarding the save file including the the location the player saved at, the amount of gold available, and any variables that you want to show the player as well.

这个插件提供了一个新的存档界面。通过这个新的界面，玩家可以直接从菜单载入或者删除存档，这也将导致存档命令一直显示在之菜单，但是我们可以关闭或者开启存档选项。从这个界面，玩家可以获得存档的各类信息，例如位置，金钱树，或者任何你想展示的变量。

***
###Instructions – Data Columns
***

For those who wish to show additional data in the save menu for each save file, you can add various data categories within the ‘Data Columns’ inside the plugin parameters. Separate each category with a comma (,). You can use the following entries for data categories:

对于那些想在每个存档显示额外信息的人，你可以添加插件参数里面的Data Columns，用逗号隔开。你可以使用下面的标签

####Data Column Categories:

	Empty
– Leaves an empty box in the category location. This won’t even show the dark rectangle in the category slot.  
显示一个空位置，但是没有外框

	Null
– Won’t draw any text, but it will draw the dark rectangle in the category slot.  
显示一个空位置，但是有外框

	Location
– Draws the current map location of the save file.		
地图坐标

	Playtime
– Draws the playtime spent for the save file.  
游戏时间

	Save Count
– Draws the number of times saved in that playthrough.  
存档数

	Gold Count
– Draws the current gold count of the safe file.  
金钱数

	Variable x
– Draws the name of the variable and value of the variable. You can use text codes in the variable name. Any text between << and >> will be not be shown when drawn. If the variable name is empty, the value will be centered.  
显示变量的名字和值。你可以使用文本代码。任何在<< >>里面的都不会被显示。如果没有变量名，变量的值就会居中

	text: stuff
	left text: stuff
	center text: stuff
	right text: stuff
– This will draw ‘stuff’ (Replace it with your own text) as text by itself with no data attached. Use ‘left’, ‘center’, or ‘right’ to decide the text alignment. If no alignment is used, it will default to ‘left’ alignment. You can use text codes within the drawn text.  
这将显示自定义文本。可以设置显示位置，默认是居左对齐。

***
###Technical – Save Modes
***

For developers who are planning to publish their RPG Maker MV games on the web, you may want to look into the ‘Technical’ parameters. Here, you can force the game into thinking the game is running on ‘local’ or ‘web’ mode. By default, you’ll want it on ‘auto’ but the forced modes are for testing purposes. Despite being for testing purposes, if you wish for your game to adjust saves as per ‘web’ mode, you can keep it that way even if your game is to be local-only. Games on the web, however, cannot use ‘local’ mode and
will automatically default to ‘web’ mode.

对于想要在网上发布游戏的开发者，你可以看一看Technical里的参数。你可以设置游戏模式，是“本地”，还是“网站”。默认你可以设置为“自动”。如果是为了测试目的，你可以在本地运行时设置web模式。如果游戏运行在网站上，你不可以使用本地模式。

***
###Technical – Save Files
***

The ‘Local Config’, ‘Local Global’, and ‘Local Save’ can have their filename format changed to your liking. Personally, I don’t recommend messing with this unless you know what you’re doing.

如果你有经验，你可以根据喜好设置'Local Config', 'Local Global', 和 'Local Save'的名字
—

However, if you are making a web-based (mobile included), I strongly suggest you look into the ‘Web Config’, ‘Web Global’, and ‘Web Save’ parameters. By default, RPG Maker MV defaults all of the saves to RPG FileX. All web-based RPG Maker MV games would then use the same configuration, same global save file, and all RPG Maker MV games played by an individual would share the same save slots. This can be very problematic.

如果你正在做网站包括移动端的游戏，我建议你看下'Web Config', 'Web Global', 和'Web Save'的参数。所以运行在网站上的游戏都会使用相同的设置。

This plugin’s default settings will solve this sharing issue by making the web save named accordingly to your game’s name provided that you keep the current plugin settings as is or adjust it accordingly. Now, your game will have its own individual identity, use its own configuration, global, and save files without clashing with any other RPG Maker MV games players may have played.

这个插件默认设置解决了网站游戏存档奔溃的一些问题

***
###Happy RPG Making!

