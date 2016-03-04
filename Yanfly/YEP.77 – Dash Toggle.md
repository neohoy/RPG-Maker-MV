##YEP.77 – Dash Toggle
***
###Introduction
***

RPG Maker MV lacks the ability to toggle dashing on and off. This plugin will enable you to toggle dashing on and off as well as provide certain traits that will inhibit the party leader from being able to dash (such as an extra heavy weapon).

MV缺乏冲刺的切换键。这个插件可以让你开启冲刺功能

***
###Notetags
***

You can use these notetags to add a disabled dashing trait. If the leading party member has a trait that disables dashing, then the player cannot dash while that actor is in the lead.


你可以使用标签来关闭冲刺特性。如果领队关闭了，玩家将不能冲刺

####Actor, Class, Weapon, Armor, and State Notetag:

	<Disable Dashing>
If the leading party member has a trait with this notetag, then the player cannot dash while that actor is in the lead.

关闭冲刺

####Plugin Commands

You can use these plugin commands to enable or disable dashing mid-game!

你可以用这个插件命令来开启或关闭

####Plugin Command

	EnableDashing
– Enables the player to be able to dash. However, this will not take priority in maps that disable dashing altogether.

开启

	DisableDashing
– Disables the player from being able to dash.

关闭

	ToggleDashing
– This will enable/disable dashing. This will not take priority in maps that disable dashing altogether.

切换

***
###Happy RPG Making!

