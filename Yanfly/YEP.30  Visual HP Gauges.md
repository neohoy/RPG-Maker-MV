## YEP.30 – Visual HP Gauges
Want to display HP gauges visibly on enemies? And possibly even your allies? Want to give certain enemies different color HP gauges or make it longer than usual? Or make it required that enemies must be defeated first before showing their HP gauge? Well, now you can!

想要显示敌方的血量吗？或者你的同伴？想要显示与平时不同的血量颜色吗？或者需要先击倒敌方才能显示血量？好的，现在可以实现了

***
### Introduction
***

This plugin requires YEP_BattleEngineCore. Make sure this plugin is located under YEP_BattleEngineCore in the plugin list.

这个插件需要战斗核心插件，请确保这个插件放在战斗核心插件下面的列表。

This plugin shows the HP Gauges of enemies as they’re selected or while they take damage. You can also opt for actors to show their HP Gauge as well. Adjust the parameters to change the way you want the HP Gauges to appear.

这个插件可以在敌方被击中或者选择时显示血量，你也可以设置队员的血量显示。你可以调整血量显示的参数。

By default, enemies would need to be defeated first in order for the gauges to show up. This can be changed within the parameter settings. However, during battle test, the HP gauges are always shown unless the enemy has a hidden HP gauge.

敌方默认不需要先击倒在显示血量。这个可以通过参数设定。但是，在编辑器战斗测试时，血量会一直显示，除非敌方隐藏。

***
### Notetags
***

#### Class and Enemy Notetags:

	<Hide HP Gauge>
	
This HP gauge will always be hidden if this notetag is present.

隐藏血量

	<Show HP Gauge>
	
This HP gauge will always be shown if this notetag is present while the target is selected or taking damage.

显示血量

	<HP Gauge Width: x>
	
This will set the battler’s HP Gauge width to x pixels. However, if this width is less than the minimum width, minimum width will take priority.

血量槽宽度，如果宽度小于最小宽度，将会取最小宽度

	<HP Gauge Height: x>
	
This set’s the HP Gauge height to x pixels.

血量槽高度

	<HP Gauge Back Color: x>
	
This changes the HP Gauge’s back color to x text color.

血量槽背景颜色

	<HP Gauge Color 1: x>
	
This changes the HP Gauge’s color 1 to x text color.

血量槽颜色1

	<HP Gauge Color 2: x>
	
This changes the HP Gauge’s color 2 to x text color.

血量槽颜色2

***
### Happy RPG Making!

