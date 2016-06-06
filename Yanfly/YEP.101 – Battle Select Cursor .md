##YEP.101 – Battle Select Cursor
***
###Introduction
***
This plugin allows you to set custom cursors when selecting allies and/or enemies for targeting while in battle. This is to help with better visual cues when picking a target if the flashing battler isn’t enough.

这个插件允许你设置自定义的战斗选择图标。这将帮助玩家获得更好的视觉体验。
***
###Instructions – Cursor Filenames
***
Save your cursor into your game project’s img/pictures folder. This will be where your project will get all of its pictures from.

将自定义图标放入img/pictures文件夹，这是你游戏项目获取图片文件的地方

The filename plays an important role in the way the cursors work. It will be used to determine the number of frames used by the cursor. It will work in the following format:

文件名在自定义效果中有重要作用。他决定这个图标的动画效果，下面是一个公式例子

	filename_WidthxHeight

Therefore, when using ‘Crystal_Blue_4x2’, it means there will be 4 frames usable from left to right and 2 frames usable from top to bottom. It will have a width of 4 frames and a height of 2.

例如，当你使用`Crystal_Blue_4x2`这样的名字，这意味着将会从左到右播放4帧，从上到下播放2帧。

If the format isn’t used, then the dimensions will default to 1×1.

如果没有设置，默认值是1×1
***
###Notetags
***
You can use the following notetags to adjust the cursor settings for your actors and enemies.

你可以使用下面的标签来设置玩家或者敌群的图标

####Actor and Enemy Notetags:

	<Battle Select Cursor: filename>
– This will change the filename of the cursor image used for this actor or enemy when selected. The same rules apply as the ones listed in the Instructions – Cursor Filenames section of the help file.

选择图标文件

	<Battle Select Cursor Anchor X: Left>
	<Battle Select Cursor Anchor X: Center>
	<Battle Select Cursor Anchor X: Right>
	<Battle Select Cursor Anchor Y: Top>
	<Battle Select Cursor Anchor Y: Middle>
	<Battle Select Cursor Anchor Y: Bottom>
– These notetags determine where the origin point of the cursor sprite should be.

这些决定图标起始位置

	<Battle Select Cursor Positon X: Left>
	<Battle Select Cursor Positon X: Center>
	<Battle Select Cursor Positon X: Right>
	<Battle Select Cursor Positon Y: Top>
	<Battle Select Cursor Positon Y: Middle>
	<Battle Select Cursor Positon Y: Bottom>
– These notetags determine where the select cursor will appear on the actor or enemy when targeting them.

这些决定着当图标出现时所在的位置

***
###Sample Cursors
***
For those who’d like some sample cursors to use, you can download these. Place them inside of your project’s /img/pictures/ folder.

如果你想要范例图标，你可以从下面下载并放入/img/pictures/文件

***
###Happy RPG Making!

