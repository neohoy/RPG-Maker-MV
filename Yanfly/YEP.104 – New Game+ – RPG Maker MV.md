##YEP.104 – New Game+ – RPG Maker MV
***
###Introduction
***

This plugin requires YEP_SaveCore. Make sure this plugin is located under YEP_SaveCore in the plugin list.

这个插件需要YEP_SaveCore，确保它放在YEP_SaveCore下面

New Game+ is a great way to provide replay value for your game. It lets the player re-experience the game in a different way with either carried over items, to carried over party members, to carried over skills, switches, and variables even. There exists many options to change how New Game+ will work for your game.

新游戏拓展是一个很好的方式来提供游戏重玩的初始值。它可以让玩家重新体验游戏，但是可以携带之前的物品，角色，技能，甚至开关或者变量。这里有很多游戏来设置你的二周目游戏。
***
###Notetags
***
There are some notetags you can utilize with a few database objects.

这里是一些你可以设置的标签

####Actor, Item, Weapon, Armor Notetag

	<No New Game+ Carry Over>
– This will prevent the item, weapon, or armor from being carried over to New Game+. If this is used on an actor, the actor will be in its default state as if a new game started.

这可以阻止特定的物品，武器，护甲被携带到二周目。如果用于角色，则这个角色将会在游戏开始时初始化。

***
###Plugin Commands
***
To set the current save to have New Game+ settings, you’ll need to use these plugin commands to alter the settings:

你可以通过这个插件命令来设置插件

####Plugin Commands:

	EnableNewGamePlus
– This will cause any save after this has been enabled to have a New Game+ option instead of the “Load” command on the loading screen.

开启二周目存档功能

	DisableNewGamePlus
– This will disable the New Game+ option for saves made after this plugin command has run. The “Load” option will appear instead of “New Game+”.

关闭二周目存档功能

***
###Happy RPG Making!

