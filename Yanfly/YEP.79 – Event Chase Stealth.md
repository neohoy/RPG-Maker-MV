##YEP.79 – Event Chase Stealth
***
###Introduction
***
This plugin requires YEP_EventChasePlayer. Make sure this plugin is located under YEP_EventChasePlayer in the plugin list. Make sure it is the most updated version of Event Chase Player.

这个插件需要YEP_EventChasePlayer，确保它放在YEP_EventChasePlayer下面，并且确保YEP_EventChasePlayer是最新版本

Grants your player the ability to go Stealth Mode for either a limited set amount of time or an unlimited amount of time. While in Stealth Mode, the player will not alert any events set by the Event Chase Player plugin. This plugin also includes region areas that are considered stealth regions.

让你的玩家可以去进入隐身模式。你可以设置隐身区域

***
###Instructions – Stealth Regions
***
Stealth Regions are places on the map that you can mark using RPG Maker MV’s region ID’s. You can decide which of the regions will be considered Stealth Regions within the Plugin Parameters or by using the following notetags inside of a map’s notebox:

隐身区域用区域ID设置。你可以用插件参数设置

	<Stealth Regions: x>
	<Stealth Regions: x, x, x>
	<Stealth Regions: x to y>
This will set regions x (or x to y) as Stealth Regions.

隐身区域ID

While the player is inside of the Stealth Region, any event that is outside of the Stealth Region cannot detect the player. However, if the player is inside of the Stealth Region and the enemy is also inside the very same Stealth Region with the matching Region ID, the enemy can detect the player.

当玩家在隐身区域，而事件不在时，不能发现玩家。但若事件也在隐身区域，则会发现

However, if the player is inside of a Stealth Region with a different ID than the Stealth Region the enemy is in, the enemy will not detect the the player.

如果，玩家所在隐身区域与事件不在一个ID，则不会发现

Once the player is detected, Stealth Regions stop applying and the alerted event will chase the player (or flee from) even if the player runs into another Stealth Region. The Stealth Regions remain disabled until the event is no longer chasing (or fleeing from) the player.

一旦玩家被发现，事件将会追逐玩家或者逃离，直到事件不再追逐，隐身区域才会重新开启

***
###Instructions – Stealth Mode
***

To enter Stealth Mode, you’ll have to utilize the plugin commands found in the plugin commands section a bit lower. While in Stealth Mode, if enabled, the Stealth Gauge will appear to alert the player how much longer the player will remain in Stealth Mode before it automatically disappears.

你可以用插件命令来更改隐身模式。一旦进入隐身模式，将会显示隐身时间槽

***
###Plugin Commands
***
You can use the following Plugin Commands to adjust Stealth Mode in your game mid-game!

你可以使用下面来更改

####Plugin Command:

	StealthTime x
– Puts the player character into Stealth Mode for x frames. Once the timer is up, the player exits Stealth Mode.

隐身时间

	StealthMode On
– Puts the player character into Stealth Mode. There is no timer for this.

隐身模式开启

	StealthMode Off
– Puts the player character out of Stealth Mode. This also resets the Stealth Timer to 0.

隐身模式关闭

	EnableStealthDash
– Enables the player to be able to dash while in Stealth Mode.

开启隐身冲刺

	DisableStealthDash
– Disables the player from being able to dash while in Stealth Mode.

关闭隐身冲刺

	SetStealthMoveSpeed x
– Sets the move speed while in Stealth Mode to x.

隐身速度

	HideStealthGauge
– This prevents the Stealth Gauge from being shown at all.

隐藏隐身槽

	ShowStealthGauge
– This will show the Stealth Gauge whenever the player is in Stealth Mode.

显示隐身槽

***
###Happy RPG Making!