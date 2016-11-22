##YEP.116 – Grid-Free Doodads – RPG Maker MV

THIS REQUIRES RPG MAKER MV 1.3.0 OR ABOVE TO WORK! Please check your rpg_core.js file to make sure it says 1.3.0 or above. If it isn’t updated, visit this thread for the update.

这个插件需要MV1.3.0以上的版本，请检查你的rpg_core.js文件内部，是否符合要求，如果不符合，请提前升级

###Introduction

In RPG Maker MV, tilesets are used for mapping purposes. Tileset A is used for drawing land while Tilesets B through E are used to add doodads. But in RPG Maker MV, doodads added by Tilesets B through E are locked to the grid and add a rather unnatural feel to it. This plugin will allow you to break free of the grid and add doodads unbound by the grid. Doodads can come in all forms, from large to small, static and animated, you name it!

在RPG Maker MV里面，图块被用来做地图。一般图块A型被用来画地面，图块B型到E型负责添加摆设物件。但是在MV里面，摆件被限定在网格上并且感觉不自然。这个插件允许你打破网格限制，添加摆件。摆件的大小，动态都可以定制。

###Instructions – Requirements

There’s a couple of things you must do in order to get this plugin working.

这个里有一系列你需要去完成的来使插件生效

1. You must have the Doodads.json inside your project’s ‘data’ folder.
2. You must have a ‘doodads’ folder inside of your project’s ‘img’ folder (unless you named it something else in the plugin parameters).
3. You must have your doodads within this folder.

>
1. 你需要把Doodads.json放入游戏data文件夹里面
2. 你需要把img文件夹里面的doodads文件夹放入游戏目录img下面
3. 你需要把你自己的摆件放入这个文件夹

You can find the above resources in the links above!

你可以在本页找到你需要的资源

###Instructions – Placing Doodads

To place doodads into your game, first, load up your game in Test Play mode. You can do this by opening up your game in RPG Maker MV, go to ‘Game’, then select ‘PlayTest’ (shortcut Ctrl+R).

为了把摆件放入你的游戏，需要现在测试模式载入你的游戏。你可以在MV里面来进入，或者用快捷键Ctrl+R

Once you’ve loaded onto a map that you want to place doodads on, press the F10 key to access the doodad editor. From there, you can select the option: ‘Place Doodads’ to start placing doodads.

一旦你载入了地图，你可以按F10键来开启编辑器，在这里你可以选择‘Place Doodads来开始放置

---
—Main Menu—
The main menu is the first menu you see when you press the F10 key on a map.

按住F10是会进入主菜单

Place Doodads
– This will take you do your doodads folder, where you can select a doodad to place on the map.

放置摆件

Edit Doodads
– This will allow you to edit the doodads that you have already placed on the map. Here, you can select which doodads based on the layer they’re on or from all doodads at once. Doodads are ordered based on their position from top to bottom, left to right.

编辑摆件

Clear Doodads
– This will clear all doodads on the map.

清除摆件

Toggle Region Overlay
– This will cause an overlay of the regions to appear on your screen to show you what tiles are affected by which regions. Use it again to hide the regions.

显示区域ID

WARNING: Using this on large maps for the first time will cause a bit of lag as the regions have to load. The larger the map, the longer the amount of time is required for it to load.

注意：如果你在一个较大的地图选择这个功能，可以需要一定的延迟来加载。

Cancel and Close
– This will remove any changes made to the doodad settings on the map and close out of the Doodad Menu.

取消并且关闭

Save and Close
– This will save any changes made to the doodad settings on the map and close out of the Doodad Menu.

保存并且关闭

---

—Doodad List—
The doodad list will show a list of all the doodads you can use for your map based on the current folder it’s in. There are three types of options you can select from here:

摆件列表

IconSet
– This will let you make a doodad out of an icon from the iconset. Take note that doodads made from icons are a bit more restrictive and cannot make use of hue changes. This will take you to a menu where you can select which icon you wish to use then go to the Doodad Placing Mode.

图标

Folders
– Folders will be marked with a / at the end of the name and will have an icon shared by all other folders. Selecting a folder will go into that folder’s contents (and further).

文件夹

Images
– Images will show a small preview of themselves to the left of the name. These images can be used as doodads without any restrictions. Selecting an image will take you to the Doodad Placing Mode.

图片

---
—Doodad Placing Mode—
When you’re in Doodad Placing Mode, you’ll notice a small section of the screen below with some instructional text.

摆件放置模式

Q E – Layer -/+
– This allows you to decrease or increase the doodad’s current layer.

提高图层和降低图层

T – Tweak Settings
– Pressing this will open up the Doodad Settings menu.

微调

W A S D – Move Screen
– This will move the screen around so you can have a clear view of the map without needing to reposition the player character.

移动屏幕

↑←↓→ – Precision Move
– Pressing the directional keys will allow you to move the doodad using the keyboard instead of the mouse. If you wish to move using the mouse, just click on the map somewhere to return control back to the mouse.

移动摆件

Z X – Place or Cancel
– Pressing Z will place the doodad in its current state on the map.
– Pressing X will return you back to the Doodad List (or the Icon Picker if you were placing a doodad made from an icon).

放置和取消

There are some hidden keyboard commands that you can use. These are rewarded to the users who read these instructions carefully. Hooray for you!

这里还有一些隐藏按键你可以使用

H – Hide/Show the Instruction Window
– Pressing H will hide the instructional window so you can get a clear view of where you’re placing the doodad. Pressing it again will make it show back up.123

H-隐藏提示窗口

1 2 3 4 5 6 7 8 9 0 – Quick Opacity Change
– The 1 through 0 keys (not NumPad) will allow you to quickly adjust the opacity level of the doodad. 1 will set 10%, 2 sets 20%, 3 sets 30%, etc. However, 0 will set 100%.

设置透明度

G – Grid Snap Menu
– This opens up the Grid Snap Menu where you can activate or deactivate Grid Snapping and the grid snapping parameters.

网格设置

R – Region Overlay
– This will cause an overlay of the regions to appear on your screen to show you what tiles are affected by which regions. Press R again to hide the regions.

显示区域ID

WARNING: Using this on large maps for the first time will cause a bit of lag as the regions have to load. The larger the map, the longer the amount of time is required for it to load.

注意：如果你在一个较大的地图选择这个功能，可以需要一定的延迟来加载。

---
—Doodad Settings—
When pressing ‘T’ during the Doodad Placing Mode or accessing individual doodads, you will come across the Doodad Settings.

摆件设置

Change Position
– Only selectable if accessed from individual doodad management. This will allow you to reposition the doodad.

设置位置

Layer
– This allows you to change the layer of the doodad. Higher layers will make the doodad appear above others (and characters) and lower layers will cause doodads to appear below.

设置图层

Hue
– Changing to hue will change the doodad’s current color shift. Be warned as this process takes up a lot of processing power, and I highly advise against using doodads of different hues if you plan to export to mobile.

设置外表色彩，这需要占用大量资源，如果你需要输出为移动端，建议不要使用不同的色彩外表

Opacity
– Changes the opacity of the doodad. When the opacity value is higher, the doodad will be less transparent. When the opacity value is lower, it will be more transparent.

透明度

Scale X, Scale Y
– This changes the amount of stretch on a doodad. X will cause a doodad to stretch horizontally while Y will cause the doodad to stretch vertically. If you decide to use a negative value, it will cause the doodad to mirror.

设置拉伸度，如果为负值，则会反向

Anchor X, Anchor Y
– This sets the base coordinates of the doodad to be located. How other doodads/objects of the same layer interact with this doodad will be based on its coordinates.

设置放置锚点

Frame Speed
– If the doodad is animated, you can adjust the frame speed of the doodad here. The number represents the number of frames that must pass before the doodad updates to the next animation cell. This means lower numbers have faster animations while higher numbers have slower animations.

设置动画速度

Blend
– Allows you to change the blend modes of the doodads. Blend modes will cause color differences based on the blend mode type to fit in with the visual effects behind it.

设置混合模式

Smooth
– Let’s you choose whether or not you want to load the doodad with either smooth or hard edges.

设置平滑模式

Delete Doodad
– Only selectable if accessed from individual doodad management. This will let you delete the doodad and then return to the doodad management list.

删除指定摆件

Revert Settings
– Cancels all of the settings made and returns back to your previous mode.

重置设置

Accept Settings
– Accepts all of the settings made and returns back to your previous mode.

应用设置

---
###Instructions – Making Your Own Doodads

Doodads only have two requirements.

摆件制作需要下面2个要求

1. They must be PNG’s.
2. They must exist within the ‘doodads’ folder (or specified folder from the plugin parameters) or within a folder inside the ‘doodads’ folder.

>
1. 他们必须是PNG格式
2. 他们必须在doodads文件夹内

If a folder is placed inside of the ‘doodads’ folder, it will be listed as on the doodads list as a directory tree to navigate through.

如果某个文件夹位于doodads内部，则会在列表中显示

####Making Animated Doodads

Doodads can be made into animated doodads. An animated doodad is one that will animate whenever the game’s graphics update. Follow these steps to make an animated doodad:

如果需要制作动态摆件，需要按照下面方法

1. Create a doodad with a cell layout similar to a sprite.
2. Each cell must be the same width and height as the other.
3. When naming the doodad, add [AxB] in its name. Replace A and B with numbers representing the number of cells horizontally (A) and the number of cells vertically (B). A doodad with 3 horizontal cells and 2 vertical cells would be named something like ‘Torch [3×2].png’.
4. The doodads cells will animate left to right. Once they reach all the way right, they will move down a row and update left to right again. The doodad named ‘Torch [3×2].png’ will update like such:

<pre>
	0 1 2
	3 4 5
</pre>

>1. 制作摆件各个单元体
>2. 每个单元图尺寸必须一致
>3. 当命名的时候，需要采用[AxB]的模式，A为横向数量，B为竖向数量。一个摆件拥有3个横向单元2个竖向单元，例如Torch [3×2].png

And that’s how you would go about the creation of an animated doodad. If this is confusing, look at some of the examples provided from Yanfly.moe.

这就是制作的步骤，如果你还是不太清楚，可以参考网站上的例子

###Happy RPG Making!

