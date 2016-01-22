## YEP.31 – Visual ATB Gauge

> Introduction--帮助文件及介绍
> 翻译 by 抖M俱乐部的 SmithJiong/bennett01/SOAP
> 转载请感谢我！ 没错上面三个都是我！

For Yanfly Engine Plugins – Battle System – ATB users, you can now display ATB gauges for your enemies! This plugin is plug and play but it does require the YEP_BattleSysATB plugin. The gauges can be shown either below or above the enemies.

对于Yanfly的ATB战斗系统插件，你现在可以让你的敌人也有行动槽啦！这个拓展插件需要ATB插件支持。行动槽可以显示在敌人下方。

This plugin requires YEP_BattleEngineCore and YEP_X_BattleSysATB. Make sure this plugin is located under YEP_BattleEngineCore and YEP_X_BattleSysATB in the plugin list.

 本插件需要YEP_BattleEngineCore和YEP_X_BattleSysATB两个前置插件请确保启用该插件时，将其放置于上述两个插件下边。
 
This plugin will show the ATB Gauge for enemies if the current battle system is ATB. The gauges can be shown either below or above the enemies.

本插件将会在ATB战斗模式下，在你敌人的上方或下方显示ATB行动槽。

### Notetags


The following are some notetags you can use to adjust the appearance of the enemy’s ATB Gauge.

下面的注释命令会帮助你进一步定制本插件的功能。

#### Enemy Notetags:

	<Show ATB Gauge>
	<Hide ATB Gauge>
>This will cause the ATB Gauge to be shown or hidden ignoring the default settings found in the parameters.

>这个命令将开启或关闭敌人的ATB行动槽显示，让你可以自己控制。

	<ATB Gauge Width: x>
>This allows you to set the enemy’s ATB Gauge width to x instead of having it match the enemy’s battler graphic width.

>你可以自定义该敌人行动槽的宽度，这通常用于你的敌人绘图不规则，而行动槽规格统一导致的显示奇葩问题，比如你可以给史莱姆等小型单位设定更小的行动槽，使其看起来更美观一点。

***

### Happy RPG Making!


