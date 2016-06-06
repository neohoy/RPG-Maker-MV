##YEP.103 – Animated Tile Option – RPG Maker MV
Some players may experience lag when walking near animated tiles. This is due to the fact that animated tiles constantly draw, delete, and redraw the tiles every few frames. Unfortunately, due to Pixi2’s drawing method, there exists some memory leaks when this kind of drawing occurs. On mobile devices or weak computers with little memory to spare, this can potentially cause some games to crash. The option to enable/disable animated tiles is now in the options menu for players to toggle.

有些玩家在接近动画图块时会感到延迟。这是因为动画图块在不断进行绘画、删除、重绘的操作。不幸的是，Pixi2渲染引擎会泄露大量的内存。在移动设备上或者配置较弱的电脑上，内存不足会使游戏崩溃。这个选项可以让玩家在设置菜单里开启或者关闭动画图块的功能。

For those who decide to make the default settings for the plugin to ‘auto’, any player who is playing on mobile or browser will default to having the setting off while local players will have the setting default to on.

对于使用默认的自动设置的人，将会在移动设备和浏览器网站关闭动画图块功能，在本地计算机会打开