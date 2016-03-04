##YEP.46 – Gab Window
***
###Introduction
***
Sometimes there’s random jibber jabber that does not warrant a message box. The Gab Window fulfills that jibber jabber by placing such text outside of the message window box and at the corner of the screen. The gab text will appear briefly and then disappear, not showing up again until the gab text is updated with something else.

有时候，通常随机的一些闲聊不需要信息框。闲聊窗口可以写上闲聊语句，并且放在信息框外面，显示在屏幕角落。闲聊文本将会短暂显示并消失，并且不会在显示

New to the MV version is the ability to play sounds for your Gab Window in addition to queueing multiple gabs together to have them form a conversation of sorts. When queued up, the currently playing gab will continue showing until it fades out before loading up the next gab.

现在的这个MV版本可以播放声音，可以为闲聊排队增加种类。当闲聊开始，初始声音会播放至到下一个闲聊语句

***
###Instructions
***

Using the Gab Window is quite simple. By default, it can be used in either the map scene or the battle scene. To call upon it, you will to use a few Plugin Commands to set up what you wish for the Gab Window to display.

使用闲聊窗口是很简单的。默认的来说，他可以用在地图或者战斗中。你可以用插件命令来显示他们

####Plugin Commands:

#####— Setup Commands —

	GabText text
This will set the gab window to type out the above text. Text codes can be used for the Gab Window.

设置闲聊语句

	GabFaceName filename
If you wish to display a face graphic, use this plugin command to have it display a face from the filename.

显示脸图

	GabFaceIndex x
Used in combination with the above plugin command to define which index the face will use.

脸图索引

	GabSpriteName filename
If you wish to display a particular character sprite, use this plugin command to have it display a sprite from the filename.

显示特别的角色形象

	GabSpriteIndex x
Used in combination with the above plugin command to define which index the sprite will use.

角色形象索引

	GabActor x
	GabActorFace x
This will display actor x’s face graphic where x is the actor’s ID.

显示角色脸图

	GabActorSprite x
This will display actor x’s sprite graphic where x is the actor’s ID.

显示角色形象

	GabParty x
	GabPartyFace x
This will display party member x’s face graphic where x is the position.

显示队伍成员脸图

	GabPartySprite x
This will display party member x’s sprite graphic where x is the position.

显示队伍成员形象

	GabSound filename
This will play a sound from the SE folder under that particular filename.

闲聊声音

#####— Display Commands —

	ShowGab
Once the above settings are complete, use this Plugin Command to launch the Gab Window and display the above data. This will put the gab data into a queue which means if there’s another gab playing, this will be next in line.

如果这个设置完，使用插件命令来显示闲聊。如果这时候有其他闲聊播放，它将会显示在下一行

Note If multiple ShowGabs are used, they will be queued up. The current playing gab will finish playing before moving onto the next. If it so happens that the inputted Gab would have the same exact settings as a previously loaded gab within the same queue, it will not be inserted to prevent any redundancy amongst the conversation.

注意如果多个ShowGabs命令被使用，他们将会排队播放。

	ForceGab
Once the above settings are complete, use this Plugin Command to clear all the other gabs in the Gab Window and display the above data.

强制清除其他闲聊，显示当前

	ClearGab
This clears out the Gab Window of the current gab and any gabs queued.

清除闲聊

***
###Happy RPG Making!

