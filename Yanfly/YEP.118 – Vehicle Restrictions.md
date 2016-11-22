##YEP.118 – Vehicle Restrictions – RPG Maker MV

###Introduction

This plugin requires YEP_RegionRestrictions. Make sure this plugin is located under YEP_RegionRestrictions in the plugin list.

这个插件需要YEP_RegionRestrictions，确保这个插件在YEP_RegionRestrictions下面

This plugin expands region restrictions (and allowed regions) to vehicles. On top of that, you can designate specific regions for vehicles to land in. This way, you can make it so that small boats cannot traverse certain bodies of watever, land in only certain spots, etc. that ships can or vice versa! Add a bit more variety to the way vehicles are handled for your game!

这个插件拓展了对交通工具的限制。你可以为交通工具设置特定的起落点，这样你就可以确保船只等可以穿过特定的水域并且停在特定码头。

###Notetags

Insert these notetags into the map noteboxes to allow for custom settings for vehicles on that map only.

把这些备注放进地图备注栏来自定义专属此地图的交通工具方式

####Map Noteboxes:

	<Boat Restrict Region: x>
	<Boat Restrict Region: x, x, x>
	<Boat Restrict Region: x to y>
	<Ship Restrict Region: x>
	<Ship Restrict Region: x, x, x>
	<Ship Restrict Region: x to y>
	<Airship Restrict Region: x>
	<Airship Restrict Region: x, x, x>
	<Airship Restrict Region: x to y>
– These notetags will caused the vehicles to be unable to move past region(s) marked with x (to y) unless the player character is given the Through ON movement flag. These regions will be combined with the regions flagged by the plugin parameters.

这些备注设置交通工具不能通行的区域

	<Boat Allow Region: x>
	<Boat Allow Region: x, x, x>
	<Boat Allow Region: x to y>
	<Ship Allow Region: x>
	<Ship Allow Region: x, x, x>
	<Ship Allow Region: x to y>
	<Airship Allow Region: x>
	<Airship Allow Region: x, x, x>
	<Airship Allow Region: x to y>
– These notetags will cause the vehicles to be able to move through these region(s) marked with x (to y). These regions will be combined with the regions flagged by the plugin parameters.

这些备注设置交通工具可以通行的区域

	<Boat Land Region: x>
	<Boat Land Region: x, x, x>
	<Boat Land Region: x to y>
	<Ship Land Region: x>
	<Ship Land Region: x, x, x>
	<Ship Land Region: x to y>
	<Airship Land Region: x>
	<Airship Land Region: x, x, x>
	<Airship Land Region: x to y>
– These notetags will enforce vehicles to only able to land on region(s) marked by x (to y). They cannot land anywhere else. These regions will be combined with the regions flagged by the plugin parameters.

这些备注设置交通工具起落的区域

###Happy RPG Making!