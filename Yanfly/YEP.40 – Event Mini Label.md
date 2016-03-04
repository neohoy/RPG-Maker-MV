##YEP.40 – Event Mini Label
This plugin lets you place text above the heads of various events using a miniature label through a comment tag. The text used can also use text codes so text, icons, colors, etc. whatever it is, you can use it as a label!

这个插件可以让你在事件头顶上使用标签。文字可以使用文本代码，所以文本，图标，颜色都是可以使用的
***
###Introduction
***
This plugin lets you place text above the heads of various events using a miniature label through a comment tag.

这个插件可以让你在事件头顶上使用标签。

***
###Comment Tags
***

Comment tags are ‘notetags’ used within the lines of an event’s comments. The reason I’m using the comment tags instead of the notetags is because each page of an event can yield a different potential name.

注解标签是使用事件注解功能做的标签。我用注解标签而不是标签栏是因为每一页事件都可以有一个不同的名字

To use this, make a comment within the event you wish to make the mini label for and insert the following:

为了使用这个功能，你需要在事件注解功能里面插入下面语句

	<Mini Label: text>
This will display the ‘text’ above the event. You can use text codes for this comment tag and it will create dynamic messages.

显示文本

	<Mini Label Font Size: x>
This will change the font size used for the mini label to x. If this tag isn’t used, the font size will be the default value in the parameters.

文本大小

	<Mini Label Y Buffer: +x>
	<Mini Label Y Buffer: -x>
This will adjust the Y buffer for the mini label by x value. If this tag isn’t used, the Y buffer will be the default value in the parameters.

文本位置

	<Always Show Mini Label>
This will make the mini label to always be shown, even when the plugin command to hide mini labels is used.

总是显示迷你标签

***
###Plugin Commands
***

If you would like to shut off the Event Mini Label mid-game or turn it on, you can use the following plugin commands:

如果你想关闭或者开启事件迷你标签，你可以使用下面插件命令

####Plugin Command:

	HideMiniLabel
Hides all Event Mini Label.

隐藏所以事件迷你标签

	ShowMiniLabel
Shows all Event Mini Label.

显示所以事件迷你标签

*** 
###Happy RPG Making!

