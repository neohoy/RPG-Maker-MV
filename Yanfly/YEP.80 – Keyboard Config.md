##YEP.80 – Keyboard Config
***
###Introduction
***
This plugin allows players to change their keyboard configuration from the in-game Options menu provided that they’re using a computer to play the game and not from a mobile device. The “Keyboard Config” option will send the player to a different screen where they can assign actions to each of the allowed keys on the keyboard.

这个插件允许你改变键盘设置。这个插件给你一个新的窗口，让你可以定义键盘按键的行为

Certain measures are made to prevent the player from locking himself or herself in the configuration screen. These measures are that the Enter keys and arrow keys cannot be changed. Almost every other key is capable of being changed to something of the player’s liking.

我们采取了一些措施来防止玩家卡死在游戏里。例如，回车键和方向键不可以被更改。几乎所以其他键都可以更改

Note: If you are using Button Common Events, place this plugin beneath Button Common Events in the plugin parameter list.

注意：如果你使用了Button Common Events，请把这个放在Button Common Events下面

***
###Button Common Event – Comment Tags
***

If you’re using Button Common Events, you can make certain Common Events able to be bound to the keyboard using Comment Tags. To make a Comment Tag, use a Comment Event inside of your Common Event, and insert the following to achieve the desired effect:

如果你使用了Button Common Events，你可以绑定事件。

####Comment Tag:

	<Config Key: text>
This is the text displayed on the keyboard if this common event is bound to a keyboard key. If this text isn’t used, then the text displayed will be the common event’s name.

显示文本

	<Config Text: text>
This is the text displayed when selecting a key to bind for the keyboard key. This is the text displayed in the selection list. If this text isn’t used, then the text displayed will be the common event’s name.

选择列表文本

	<Config Required>
This makes the common event required to be bound on the keyboard before the player can exit the configuration menu. In order for this to work properly, there needs to be a Button Common Event bound for this common event as well.

必须绑定事件

***
###Happy RPG Making!