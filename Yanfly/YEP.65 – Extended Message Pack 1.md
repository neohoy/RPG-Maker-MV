##YEP.65 – Extended Message Pack 1
***
###Introduction
***

This plugin requires YEP_MessageCore.js to run. Place this plugin under YEP_MessageCore.js in the plugin list.

这个插件需要YEP_MessageCore.js，确保它放在YEP_MessageCore.js下面

This plugin extends the amount of things the Message system can do in RPG Maker MV. These features range from text sounds, more name window options, face index control, hex colors, extended choice controls, and more precise window positioning control. New text codes are also added to further ease the usage of the message window.

这个插件拓展了信息系统的很多功能。从文本声音，到更多的名字窗口选项，脸图，索引，文本样式，选项控制，窗口位置设置等。新的文本代码也被添加进来

####Text Codes

By using certain text codes in your messages, you can have the game replace them with the following:

你可以使用下面的文本代码

***
###Plugin Commands
***

You can use the following plugin commands to adjust a few of the settings regarding the Message Window.

你可以使用下面的插件命令来调整

####Plugin Commands

— Letter Sounds —

	EnableLetterSound
	DisableLetterSound
– These commands will enable or disable the letter sounds respectively.

开启或关闭文本声音

	LetterSoundName Cursor2
– This will replace the current letter sound with the written filename. The filename is case sensitive. Do not use the file extension.

设置文本声音

	LetterSoundVolume 100
– This will change the letter sound volume to 100.

设置文本声音音量

	LetterSoundPitch 125
– This will change the letter sound pitch to 125.

设置文本声音音调

	LetterSoundPitchVariance 10
– This will cause the letter sound’s pitch to fluctuate between -10 & 10.

设置文本声音音调浮动

	LetterSoundPan 0
– This will change the letter sound’s pan to 0.

设置文本声音音域

	LetterSoundPanVariance 10
– This will cause the letter sound’s pan to fluctuate between -10 and 10.

设置文本声音音域浮动

	LetterSoundInterval 2
– This will change the interval at which the letter sounds are played to 2 letters. Change it to 0 to play on every letter written out.

设置文本声音间隔

	LetterSoundReset
– This will reset the letter sounds to their default settings.

重置文本声音

— Choice Settings —

	ChoiceRowMax 4
– This will set the maximum amount of visible choices to 4.

最大可选择排为4排

— Message Window Positions —

	MessageRows 6
– Changes the Message Rows displayed to 6. If you are using continuous Show Text events, this will continue displaying the following lines’s texts until it hits the row limit. Anything after that is cut off until the next message starts to avoid accidental overlap.

信息框可显示6排

	MessageWidth 400
– Changes the Message Window Width to 400 pixels. This will cut off any words that are shown too far to the right so adjust accordingly!

信息框宽度400

	MessagePositionX 300
– Sets the Message Window’s X Position to 300. This position will be* relative to its horizontal anchor point.

信息框x位置为300

	MessagePositionY 400
– Sets the Message Window’s Y Position to 400. This position will be relative to its vertical anchor point.

信息框Y位置为400

	MessagePositionXAuto
– Sets the Message Window’s X Position to be automatically fitted and not set relative to its vertical anchor point.

信息框自动调整x位置

	MessagePositionYAuto
– Sets the Message Window’s Y Position to be automatically fitted and not set relative to its vertical anchor point.

信息框自动调整y位置

	MessageAnchorX left
– Sets the Message Window’s x anchor to ‘left’, ‘center’, or ‘right’ if you are using specified coordinates.

信息框基准点靠左

	MessageAnchorY bottom
– Sets the Message Window’s y anchor to ‘left’, ‘center’, or ‘right’ if you are using specified coordinates.

信息框基准点在底部

	MessagePositionReset
– Resets both the Message Window’s X and Y Positions to its automatic positions and not adjusted to its anchor points. The Message Width and the Message Rows.

信息框位置重置

***
###Happy RPG Making!