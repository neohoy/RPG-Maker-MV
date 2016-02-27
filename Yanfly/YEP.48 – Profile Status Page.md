##YEP.48 – Profile Status Page


***
###Introduction
***

This plugin requires YEP_StatusMenuCore.js.
Place this plugin under YEP_StatusMenuCore.js in the Plugin Manager.

这个插件需要YEP_StatusMenuCore，确保它在YEP_StatusMenuCore下面

This plugin adds a new ‘Profile’ command to the Status Menu where the player can read up on the actor’s biography. Pictures can be added in. Text can be updated mid-game, too!

这个插件需要身份菜单核心插件。这个插件添加了“概述”命令，在这里玩家可以阅读角色的出生历史。在这里可以添加图片。文本也可以在游戏中更新

***
###Notetags
***

The following notetags are used for actors specifically to alter the profile page properties for the Status Menu.

下面这个标签可以更加具体改变角色的个人信息概述

####Actor Notetags:
	<Profile Text>
	text
	text
	</Profile Text>
Changes the profile text from the default profile text to the text used in between the two notetags. You can use text codes for the text here. Word wrap is not supported.

改变默认的个人信息概述。你可以使用文本代码。不支持文字的自动换行。

	<Profile Image: filename>
If you wish to associate a profile image for the actor, replace ‘filename’ with the filename of a picture located in your img/pictures folder. Do not include the file extension. If your image is Aldo.png, just use ‘Aldo’ and do not include the ‘.png’ extension.

如果你希望设定角色的个人概述图片，可以用文件名代替filename，不需要包含拓展名。如果你的图片是Aldo.png，你使用Aldo即可，不需要.png。

	<Profile Image Align: Left>
	<Profile Image Align: Center>
	<Profile Image Align: Right>
If you wish to use a different alignment from the one in the plugin’s parameter settings, you can use these notetags. If you use a nonexistant word, then the right alignment will be decided by default.

如果你想设置不同的位置，可以使用这个标签。如果你没用，则会默认右侧

***
###Plugin Commands
***
The following plugin commands can be used to alter an actor’s profile page.

下面的插件命令可以用来改变角色概况页

####Plugin Commands:

	ClearProfileText actorId
This will clear out all of actorId’s profile text.

清除角色概况文本

	AddProfileText actorId text
This will add to actorId’s profile text the line of text.

增加角色概况文本

	ProfileTextLine lineIndex actorId text
This will change the specific lineIndex of the profile text for actorId to display a specific text. For example, if you wish to the 50th line of the profile text for actor 3 to ‘Hello World’, you’ll write this out as the plugin command: ProfileTextLine 49 3 Hello World

你可以改变角色文本概述特定行的文本。例如如果你希望角色ID3的人物概述第50行为‘Hello World’，你可以这么写：ProfileTextLine 49 3 Hello World


	ProfileImage actorId filename
This will change the profile image for actorId to filename without the file extension. For example, if you wish to change actor 3’s profile image to Aldo.png, you’ll write out this as the plugin command:  ProfileImage 3 Aldo

这可以改变角色概述的图片显示。例如你想改变角色ID3的概述图片为Aldo.png，你可以这么写ProfileImage 3 Aldo

	ProfileImageAlign actorId align
This will change the profile image alignment for actorId. Replace ‘align’ with ‘left’, ‘center’, or ‘right’ without the quotes. If a nonexistant word is used for the alignment, then the right alignment will be used. If you wish to make the image aligned to the left for actor 3, you’ll use: ProfileImageAlign 3 Left

这可以改变概述图片位置。可以用‘left’, ‘center’, 或者‘right’ 替代‘align’。如果没有没写，默认是右侧。如果你想要让角色ID3图片在左侧，你可以用ProfileImageAlign 3 Left

***
###Happy RPG Making!

