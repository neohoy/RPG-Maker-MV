##YEP.81 – FPS Synch Option

RPG Maker MV is constructed in a way where each update to its engine is done once per frame update. While this is normally fine, as many players view the game through 60 fps, some players experience the game differently as their hardware may run at higher than 60 fps.

MV是基于帧来更新的。通常这样表现不错，因为大多数玩家的FPS都在60，但是有些玩家超过60就会非常不舒服

When RPG Maker MV version 1.1.0 is implemented, it implemented Galenmereth’s fluid timestep, which forces the game to always play as if it is 60 fps. In practice, this is great for everybody because players that experience more 60 fps will be able to play the game as if it was 60 fps.

MV升级到1.1.0后，基于时间流来行走，这就强制玩家在60fps游戏。实际上，这样是有效果的，对于他们能够超过60fps来说，这样就可以保证游戏

However, there comes a problem when a player’s hardware isn’t strong enough to support RPG Maker MV natively at 60 fps (such as the case with older computers, or weaker mobile devices) or if the player is using video recording software that goes below 60 fps. The game will appear laggy and jumping without good response rates from input commands or possibly even make the player miss out on certain visual frame updates.

可是对于一些老旧设备，不能支持MV到60fps的时候，游戏将会卡顿。

This plugin places a setting in the Options menu to enable or disable the fluid timestep addition and utilize the former RPG Maker MV engine updating function. This way, players will have the option of using fluid timesteps or opting to not use it instead of forcing it on everybody who may not be able to handle it.

这个插件可以让设置菜单能够开启同步选项。这样，玩家就可以选择是否基于时间流来运行游戏

***
###Happy RPG Making!