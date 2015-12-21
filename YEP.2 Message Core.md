## YEP.2 Message Core
The Message Core plugin adds more functionality to the default RPG Maker MV message system, enabling more text codes, a name box, and adjustable message window sizes!

这个信息核心插件为RPG Maker MV的默认信息系统添加了很多功能，可以使用更多的文本代码，名字框，甚至可以调整文本框大小

***
- ### Introduction
***

While RPG Maker MV Ace certainly improved the message system a whole lot, it wouldn’t hurt to add in a few more features, such as name windows, converting textcodes to write out the icons and/or names of items, weapons, armours, and* more in quicker fashion. This script also gives the developer the ability to adjust the size of the message window during the game, give it a separate font, and to give the player a text fast-forward feature.

当RPG Maker MV Ace改善了信息系统以后，我们很伤心的发现只有很少的特点，例如名字框，文本代码转换为图标或者物品、武器、装备的名字，以及更多流行的地方。这个脚本可以让开发者自行调整消息框的大小，调整字体或者文本快进的特点

***
- ### Word Wrapping
***

Word wrapping is now possible through the message system. You can enable and disable Word wrap using Plugin Commands. While using word wrap, if the word is to extend past the message window’s area, it will automatically go to the following line. That said, word wrap will disable the editor’s line breaks and will require you to use the ones provided by the plugin:

文本换行功能现在可以通过信息系统来调整。你也可以使用插件命令来开启和关闭这个换行功能。当开启文本换行的时候，当你的问题超过了文本框的大小，它将会自动转入下一行。也就是说，文本换行将会关闭编辑器的文本换行功能，并且要求你用下面的代码来实现。

	<br> 
    <line break> 
> is text code to apply a line break. Use this before or after a part in which you wish to start a new line.

> 这段代码可以实现换行，当你打算换行的时候，请在的一段之前或者之后添加。

***
- ### Text Codes
***

By using certain text codes in your messages, you can have the game replace them with the following:

通过使用这些文本命令，你可以通过以下方式替代他们

**Text Code Function**

	\V[n] Replaced by the value of the nth variable.
	显示变量的值
	
	\N[n] Replaced by the name of the nth actor.
	显示角色的名字
	
	\P[n] Replaced by the name of the nth party member.
	显示队伍成员的名字
	
	\G Replaced by the currency unit.
	显示货币
	
	\C[n] Draw the subsequent text in the nth color.
	随后文本的颜色
	
	\I[n] Draw the nth icon.
	显示图标
	
	\{ Increases the text size by one step.
	增大一号文本大小
	
	\} Decreases the text size by one step.
	减少一号文本大小
	
	\\ Replaced with the backslash character.
	反斜线的文字
	
	\$ Opens the gold window.
	打开金币框
	
	\. Waits 1/4th seconds.
	等待0.25秒
	
	\| Waits 1 second.
	等待1秒
	
	\! Waits for button input.
	等待按钮按下
	
	\> Display remaining text on same line all at once.
	在同一行显示文字
	
	\< Cancel the effect that displays text all at once.
	取消显示所有文字
	
	\^ Do not wait for input after displaying text.
	显示文本后不需要等待

**Wait: Effect:**

	\w[x] – Waits x frames (60 frames = 1 second). Message window only.
	等待x时间。只对信息框有效。

**NameWindow: Effect:**

	\n<x> – Creates a name box with x string. Left side. *Note
	建立靠左的名字框
	
	\nc<x> – Creates a name box with x string. Centered. *Note
	建立居中的名字框
	
	\nr<x> – Creates a name box with x string. Right side.*Note
	建立靠右的名字框
	
	*Note: Works for message window only.
	只对信息框有效

**Line Break Effect:**

	<br> – If using word wrap mode, this will cause a line break.
	如果你使用了换行模式，这将导致换行

**Position: Effect:**

	\px[x] – Sets x position of text to x.
	设置文本位置为x
	
	\py[x] – Sets y position of text to y.
	设置文本位置为y
	
**Outline: Effect:**

	\oc[x] – Sets outline colour to x.
	设置轮廓颜色
	
	\ow[x] – Sets outline width to x.
	设置轮廓宽度

**Font: Effect:**

	\fr – Resets all font changes.
	重置文本的改变
	
	\fs[x] – Changes font size to x.
	改变文本大小
	
	\fn<x> – Changes font name to x.
	改变文本字体
	
	\fb – Toggles font boldness.
	加粗
	
	\fi – Toggles font italic.
	倾斜

**Actor: Effect:**

	\af[x] – Shows face of actor x. *Note
	显示角色脸图
	
	\ac[x] – Writes out actor’s class name.
	显示角色职业
	
	\an[x] – Writes out actor’s nickname.
	显示角色昵称
	
	*Note: Works for message window only.
	只对信息框有效
	
**Party: Effect:**

	\pf[x] – Shows face of party member x. *Note
	显示队伍成员脸图
	
	\pc[x] – Writes out party member x’s class name.
	显示队伍成员昵称
	
	\pn[x] – Writes out party member x’s nickname.
	显示队伍成员的昵称
	
	*Note: Works for message window only.
	只对信息框有效

**Names: Effect:**

	\nc[x] – Writes out class x’s name.
	显示职业名
	
	\ni[x] – Writes out item x’s name.
	显示物品名
	
	\nw[x] – Writes out weapon x’s name.
	显示武器名
	
	\na[x] – Writes out armour x’s name.
	显示装备名
	
	\ns[x] – Writes out skill x’s name.
	显示技能名
	
	\nt[x] – Writes out state x’s name.
	显示状态名
	
**Icon Names: Effect:**

	\ii[x] – Writes out item x’s name including icon.
	显示包括图标的物品名
	
	\iw[x] – Writes out weapon x’s name including icon.
	显示包括图标的武器名
	
	\ia[x] – Writes out armour x’s name including icon.
	显示包括图标的装备名
	
	\is[x] – Writes out skill x’s name including icon.
	显示包括图标的技能名
	
	\it[x] – Writes out state x’s name including icon.
	显示包括图标的状态名

And those are the text codes added with this script. Keep in mind that some of these text codes only work for the Message Window. Otherwise, they’ll work for help descriptions, actor biographies, and others.

这些文本代码已经添加进了脚本。请注意这里面有一部分文本代码只能用于消息框。而另外一些，可以对于描述文字，角色描述或者其他起作用。

***
- ### Plugin Commands
***

The following are some plugin commands you can use through the Event Editor to change various aspects about the Message system.

你可以通过事件编辑器使用下面这些插件命令来改变信息系统很多方面

**Plugin Comand**

	MessageRows 6
	
> Changes the Message Rows displayed to 6. If you are using continuous Show Text events, this will continue displaying the following lines’s texts until it hits the row limit. Anything after that is cut off until the next message starts to avoid accidental overlap.

> 将信息可显示行数改为6行。如果你连续使用显示文本的事件，这将导致文本会一直显示在框内直到达到设定上限。在这之后的文字将会显示在下一个文本框开始的时候，以免造成不必要的重叠。

	MessageWidth 400
	
> Changes the Message Window Width to 400 pixels. This will cut off any words that are shown too far to the right so adjust accordingly!

> 将文本框宽度改为400像素。这将把任何超过这个像素的文字删掉。

***

### Happy RPG Making!

