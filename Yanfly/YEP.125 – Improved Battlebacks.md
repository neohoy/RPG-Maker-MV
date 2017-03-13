##YEP.125 – Improved Battlebacks – RPG Maker MV
###Introduction

This plugin remakes how RPG Maker MV handles battlebacks. By default, all battlebacks are handled in a hard-structured fashion making them hard to modify and alter to behave dynamically. This plugin reworks the way RPG Maker MV’s battlebacks behave using a more automatic and flexible means of handling them, allowing battlebacks to added, removed, change its image, fade in/out, adjust opacity settings, and scroll in various directions!

这个插件重新制作了背景系统。MV软件默认对背景有非常严格的管控，因此我们很难把背景调整的更加充满活力。这个插件可以让MV对背景的管控更加弹性和自动化，你可以改变背景，设置渐入渐出向，调整透明度或者让背景滚动播放。

If you are using YEP_CoreEngine and YEP_BattleEngineCore, place this plugin under both of those plugins in the plugin list to ensure compatibility. The action sequences provided by this plugin can only be used if the plugin YEP_BattleEngineCore is installed in the plugin list above this plugin.

如果你使用了YEP_CoreEngine和YEP_BattleEngineCore，请把这个插件放在他们下面来保障兼容性。只有YEP_BattleEngineCore在这个插件之上时，战斗序列才会生效。

###Plugin Commands

You can use the following plugin commands to alter how battlebacks behave in your game. Keep in mind that these plugin commands must be used while the party is in battle.

你可以使用下面的插件命令来改变背景，请记住这些命令需要在战斗阶段使用
—

	BATTLEBACK id ADD: folder, filename
	BATTLEBACK id ADD: folder, filename, hue
– Replace ‘id’ with the battleback you wish to alter as a number larger than 2 (i.e. 3 or above). Replace ‘folder’ with the exact folder name in your project’s ‘img’ folder (case sensitive). Replace ‘filename’ with the image filename without the file extension (case sensitive). If ‘hue’ is used, replace ‘hue’ with a number between 0 and 360 to change the hue of the image used. This will add a new battleback stacked on top of battlebacks 1 and 2 with higher ID’s being on top. When newly added, the new battleback will start at opacity 0 and fade in with a duration of 20 frames.

在本命令中，你可以添加指定id的图片尾背景。id可以替换为任意大于2的数值，例如3或者更高。folder可以替换为你img文件夹内的子文件夹。filename可以替换为不带拓展名的图片文件作为背景。hue可以替换为0-360的数值来改变色调。这个命令可以叠加一个背景在原有背景之上，新背景将会以透明度0进场，并在20帧之内渐变出现。

	BATTLEBACK id REMOVE
– Replace ‘id’ with the battleback you wish to alter as a number larger than 2 (i.e. 3 or above). This will remove the battleback from being shown. When this command is used, the battleback will fade with a duration of 20 frames. Once it reaches 0 opacity, the battleback will be removed from the battle.

这个命令可以移除指定id的背景。背景将会在20帧内渐出，当背景透明度达到0时，将会移除这个背景。

	BATTLEBACK id CHANGE TO: folder, filename
	BATTLEBACK id CHANGE TO: folder, filename, hue
– Replace ‘id’ with the battleback you wish to alter. Replace ‘folder’ with the exact folder name in your project’s ‘img’ folder (case sensitive). Replace ‘filename’ with the image filename without the file extension (case sensitive). This will change the designated battleback’s image to use the desired image depicted by the folder and filename. If ‘hue’ is used, replace ‘hue’ with a number between 0 and 360 to change the hue of the image used.

这个命令可以替换指定id的背景。

	BATTLEBACK id FADE OUT
	BATTLEBACK id FADE OUT: duration
	BATTLEBACK id FADE IN
	BATTLEBACK id FADE IN: duration
– Replace ‘id’ with the battleback you wish to alter. This will cause the designated battleback to fade out/in. If ‘duration’ is used, replace it with a number to indicate how many frames will be used for the fade out/in. If no duration is specified, it will default to 20 frames.

这个命令可以设置背景渐入渐出效果和持续时间

	BATTLEBACK id OPACITY: n
	BATTLEBACK id OPACITY: n%
– Replace ‘id’ with the battleback you wish to alter. Replace ‘n’ with the opacity value you wish to achieve (from 0 to 255) or replace ‘n%’ with the opacity rate you wish to set the battleback to (from 0% to 100%). This will set the designated battleback’s opacity to that value. If there are any fade in or out commands occurring as this command is issued, they’ll be disabled.

这个命令可以设置背景透明度

	BATTLEBACK id SCROLL SPEED X: +n
	BATTLEBACK id SCROLL SPEED X: -n
	BATTLEBACK id SCROLL SPEED Y: +n
	BATTLEBACK id SCROLL SPEED Y: -n
– Replace ‘id’ with the battleback you wish to alter. Replace ‘n’ with the value you wish to change the scroll speed X or scroll speed Y of. The higher the ‘n’ value, the faster it scrolls.

这个命令可以设置背景滚动速度

	BATTLEBACK id RESET SCROLL SPEED
– Replace ‘id’ with the battleback you wish to alter. Resets the scroll speeds for X and Y back to 0.

这个命令可以重置背景滚动速度为0

###Yanfly Engine Plugins – Battle Engine Extension – Action Sequence Commands

If you have YEP_BattleEngineCore.js installed with this plugin located underneath it in the Plugin Manager, you can make use of these extra damage related action sequences.

如果你使用了YEP_BattleEngineCore.js，你可以将这些命令用在战斗序列之中

<pre>

BATTLEBACK id ADD: folder, filename
BATTLEBACK id ADD: folder, filename, hue

Replace ‘id’ with the battleback you wish to alter as a number larger than 2 (i.e. 3 or above). Replace ‘folder’ with the exact folder name in your project’s ‘img’ folder (case sensitive). Replace ‘filename’ with the image filename without the file extension (case sensitive). If ‘hue’ is used, replace ‘hue’ with a number between 0 and 360 to change the hue of the image used. This will add a new battleback stacked on top of battlebacks 1 and 2 with higher ID’s being on top. When newly added, the new battleback will start at opacity 0 and fade in with a duration of 20 frames.

战斗中添加背景

Usage Example: battleback 3 add: battlebacks1, GrassMazePool
battleback 4 add: battlebacks2, GrassMaze, 180

</pre>
<pre>


BATTLEBACK id REMOVE

Replace ‘id’ with the battleback you wish to alter as a number larger than 2 (i.e. 3 or above). This will remove the battleback from being shown. When this command is used, the battleback will fade with a duration of 20 frames. Once it reaches 0 opacity, the battleback will be removed from the battle.

战斗中移除背景

Usage Example: battleback 3 remove
battleback 4 remove

</pre>
<pre>


BATTLEBACK id CHANGE TO: folder, filename
BATTLEBACK id CHANGE TO: folder, filename, hue

Replace ‘id’ with the battleback you wish to alter. Replace ‘folder’ with the exact folder name in your project’s ‘img’ folder (case sensitive). Replace ‘filename’ with the image filename without the file extension (case sensitive). This will change the designated battleback’s image to use the desired image depicted by the folder and filename. If ‘hue’ is used, replace ‘hue’ with a number between 0 and 360 to change the hue of the image used.

战斗中改变背景

Usage Example: battleback 1 change to: parallaxes, SeaofClouds
battleback 2 change to: battlebacks2, Ship, 180

</pre>
<pre>


BATTLEBACK id FADE OUT
BATTLEBACK id FADE OUT: duration
BATTLEBACK id FADE IN
BATTLEBACK id FADE IN: duration

Replace ‘id’ with the battleback you wish to alter. This will cause the designated battleback to fade out/in. If ‘duration’ is used, replace it with a number to indicate how many frames will be used for the fade out/in. If no duration is specified, it will default to 20 frames.

战斗中背景效果

Usage Example: battleback 1 fade out
battleback 2 fade out: 120
battleback 1 fade in
battleback 2 fade in: 180

</pre>
<pre>


BATTLEBACK id OPACITY: n
BATTLEBACK id OPACITY: n%

Replace ‘id’ with the battleback you wish to alter. Replace ‘n’ with the opacity value you wish to achieve (from 0 to 255) or replace ‘n%’ with the opacity rate you wish to set the battleback to (from 0% to 100%). This will set the designated battleback’s opacity to that value. If there are any fade in or out commands occurring as this command is issued, they’ll be disabled.

战斗中改变背景透明度

Usage Example: battleback 1 opacity: 127
battleback 2 opacity: 50%

</pre>
<pre>


BATTLEBACK id SCROLL SPEED X: +n
BATTLEBACK id SCROLL SPEED X: -n
BATTLEBACK id SCROLL SPEED Y: +n
BATTLEBACK id SCROLL SPEED Y: -n

Replace ‘id’ with the battleback you wish to alter. Replace ‘n’ with the value you wish to change the scroll speed X or scroll speed Y of. The higher the ‘n’ value, the faster it scrolls.

战斗中改变背景滚动速度

Usage Example: battleback 1 scroll speed x: +1
battleback 1 scroll speed y: +2
battleback 2 scroll speed x: -3
battleback 2 scroll speed y: -4

</pre>
<pre>


BATTLEBACK id RESET SCROLL SPEED

Replace ‘id’ with the battleback you wish to alter. Resets the scroll speeds for X and Y back to 0.

战斗中重置背景滚动速度

Usage Example: battleback 1 reset scroll speed

</pre>


###Enjoy!

