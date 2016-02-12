## YEP.4 – Action Sequence Pack 1

The first of three action sequence packs to be made for YEP’s Battle Engine Core! This pack includes action sequences that are mechanics-related for your actions.

这是为战斗核心系统制作的三个行动序列拓展包的第一个。这个拓展为你的动作添加了技术上的支持

***
### Action Sequences – Action List
***

The following contains a list of the actions you can use inside the five action sequences. Each action has a unique function and requires certain formats to operate properly.

下面这个列表包含了你可以在动作序列里执行的动作。每一个动作都有单独的功能并且需要明确的代码来开启。

#### ADD stat BUFF: target, (turns), (show)  
Affects the target with ‘stat’ buff. Replace ‘stat’ with ‘hp’, ‘mp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. If you include a number after the target, it will buff the target by that many turns. Include ‘show’ and it will show the target getting the buff applied in the battle log.  

Usage Example: 

	add atk buff: user, 3, show
	add def buff: target, 8

增益状态效果的影响。你可以使用生命值，魔法值，攻击，防御，魔法，魔法防御，敏捷或者幸运来替代状态。目标后的数字是它会持续的回合数，你也可以将增益效果显示在战斗页面。

#### ADD stat DEBUFF: target, (turns), (show)
Affects the target with ‘stat’ debuff. Replace ‘stat’ with ‘hp’, ‘mp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. If you include a number after the target, it will debuff the target by that many turns. Include ‘show’ and it will show the target getting the debuff applied in the battle log.

Usage Example: 

	add atk debuff: user, 3, show
	add def debuff: target, 8

减益状态效果的影响。你可以使用生命值，魔法值，攻击，防御，魔法，魔法防御，敏捷或者幸运来替代状态。目标后的数字是它会持续的回合数，你也可以将增益效果显示在战斗页面。

#### ADD STATE X: target, (show)
#### ADD STATE X, Y, Z: target (show)
Affects the target with X state (including Y and Z if used in that format). If ‘show’ is included, it will display any state related messages.

Usage Example: 

	add state 5: target
	add state 6, 7, 8: user, show

影响目标状态X,如果公式内包含Y,Z也可以输入。你可以将其显示在战斗页面。

#### ANIMATION X: target, (mirror)

Plays animation X on target. ‘Mirror’ will cause the animation to appear mirrored. Keep in mind that animations played on actors will automatically be mirrored and setting the mirror option will reverse it and have it appear unmirrored.

Usage Example: 
	
	animation 5: user
	animation 6: target, mirror

在目标身上播放动画X。镜像选项将会动画镜像化。想象一下角色身上的动画会自动镜像播放。设置镜像选项将会关闭镜像功能。

#### BGM: STOP
#### BGM: MEMORIZE
#### BGM: MEMORY
#### BGM: filename, (volume), (pitch), (pan)

Changes the current background music at hand. ‘Stop’ will stop any BGM from playing. ‘Memorize’ will memorize the current BGM. ‘Memory’ will replay the memorized BGM if there is one playing. If you choose a filename (without the filename extensions), the game will play that BGM instead. Using this option opens up access to the volume, pitch, and pan control, all of which are optional to use. If no values are inputed for volume, pitch, and pan, the game will use the settings in this plugin’s parameters.

Usage Example: 

	bgm: stop
	bgm: memorize
	bgm: memory
	bgm: Battle7
	bgm: Theme2, 80, 100, 0

手动改变背景音乐。停止选项将会停止播放。记忆选项将会记住当前音乐。回忆选项将会播放记住的音乐。如果你选择文件名，游戏会播放它。使用这个选项可以控制音量，场景和管理。如果你没有输入相关数值，它将启用默认的插件参数。

#### BGS: STOP
#### BGS: MEMORIZE
#### BGS: MEMORY
#### BGS: filename, (volume), (pitch), (pan)
Changes the current background sound at hand. ‘Stop’ will stop any BGS from playing. ‘Memorize’ will memorize the current BGS. ‘Memory’ will replay the memorized BGS if there is one playing. If you choose a filename (without the filename extensions), the game will play that BGS instead. Using this option opens up access to the volume, pitch, and pan control, all of which are optional to use. If no values are inputed for volume, pitch, and pan, the game will use the settings in this plugin’s parameters.

Usage Example: 

	bgs: stop
	bgs: memorize
	bgs: memory
	bgs: City
	bgs: Darkness, 80, 100, 0

手动改变背景声效。停止选项将会停止播放。记忆选项将会记住当前声效。回忆选项将会播放记住的声效。如果你选择文件名，游戏会播放它。使用这个选项可以控制音量，场景和管理。如果你没有输入相关数值，它将启用默认的插件参数。

#### CHANGE SWITCH X: on/off/toggle/switch z
#### CHANGE SWITCH X..Y: on/off/toggle/switch z
#### CHANGE SWITCH X TO Y: on/off/toggle/switch z

Changes Game Switch X to on, off, toggle (switching between on/off), or to whatever value the switch y is.

Usage Example: 

	change switch 1: on
	change switch 2..4: off
	change switch 5 to 8: toggle
	change switch 9: switch 5

改变游戏开关或者其开关的值。

#### CHANGE VARIABLE X = Y
#### CHANGE VARIABLE X += Y
#### CHANGE VARIABLE X -= Y
#### CHANGE VARIABLE X *= Y
#### CHANGE VARIABLE X /= Y
#### CHANGE VARIABLE X %= Y

Changes variable X in the middle of the action sequence to be modified by value Y. Y can be either an integer or a piece of code.

Usage Example: 

	change variable 1 = 2
	change variable 3 += 4
	change variable 5 -= 6
	change variable 7 *= 8
	change variable 9 /= 10
	change variable 11 %= 12

在战斗当中通过Y改变变量X的值。X,Y可以是整数或者代码。
#### COLLAPSE: target, (force)

If the target is to be dead at this point, this will be the point in the action sequence where you can promt the game to kill the target as long as the target has 0 HP. If you want to force the death of the target, include the ‘force’ command after the targets.

Usage Example: 

	collapse: user
	collapse: target, force

如果目标死亡，当你在攻击目标时，只要目标血量降为0，就可以让其成为行动序列的一部分。如果你想强制目标死亡，请使用force命令。
#### COMMON EVENT: X

Plays common event X at that point in the action sequence. Nothing else will continue until the common event is finished.

Usage Example: 

	common event: 1

在行动序列中执行公共事件X。在事件执行完毕之前不会有其他动作。
#### EVAL: code

For those who’d like to do something that the current Battle Engine doesn’t support, you can use an eval function to have a piece of code occur. Users beware, for those unfamiliar with JavaScript should avoid handling this action sequence command.

Usage Example: 

	eval: $gameParty.loseItem($dataItems[3], 10)
对于有些想完成当前游戏战斗系统不支持的事情的人，你可以使用代码来实现。使用者应注意，对于不熟悉JS命令的人，请避免使用这个命令。
#### GAIN ITEM X: Y LOSE ITEM X: Y
#### GAIN WEAPON X: Y LOSE WEAPON X: Y
#### GAIN ARMOR X: Y LOSE ARMOR X: Y

Your party will gain/lose item x, weapon x, or armor x in the amount of y. If you choose to omit y, it will default to 1.

Usage Example: 

	gain item 1: 20
	lose weapon 2
	gain armor 3: 50

#### GOLD +x
#### GOLD -x

Your party will gain/lose gold in the middle of battle by x amount.

Usage Example: 

	gold +2000
	gold -500

#### HP +X: target, (show)
#### HP -X: target, (show)
#### HP +X%: target, (show)
#### HP -X%: target, (show)
#### HP +VARIABLE X: target, (show)
#### HP -VARIABLE X: target, (show)
#### HP +VARIABLE X%: target, (show)
#### HP -VARIABLE X%: target, (show)

Target(s) gains HP equal to X values. To show the popup, insert ‘show’ after the target in the action sequence line. Including ‘show’ is entirely optional. If ‘show’ is omitted, no popup will be displayed.

Usage Example: 

	hp +500: user
	hp -variable 5: target
	hp +25%: target
	hp -variable 7: user

#### ME: STOP
#### ME: filename, (volume), (pitch), (pan)

Causes the battle to play a music fanfare. ‘Stop’ will stop any ME from playing. If you choose a filename (without the filename extensions), the game will play that ME instead. Using this option opens up access to the volume, pitch, and pan control, all of which are optional to use. If no values are inputed for volume, pitch, and pan, the game will use the settings in this plugin’s parameters.

Usage Example:

	me: stop
	me: Victory1
	me: Darkness, 80, 100, 0

#### MP +X: target, (show)
#### MP -X: target, (show)
#### MP +X%: target, (show)
#### MP -X%: target, (show)
#### MP +VARIABLE X: target, (show)
#### MP -VARIABLE X: target, (show)
#### MP +VARIABLE X%: target, (show)
#### MP -VARIABLE X%: target, (show)

Target(s) gains MP equal to X values. To show the popup, insert ‘show’ after the target in the action sequence line. Including ‘show’ is entirely optional. If ‘show’ is omitted, no popup will be displayed.

Usage Example: 

	mp +500: user
	mp -variable 5: target
	mp +25%: target
	mp -variable 7: user

#### REFRESH STATUS

Refreshes the status window in the middle of an action sequence.

Usage Example: 

	refresh status

#### REMOVE stat BUFF: target, (show)

Removes the ‘stat’ buff from target. Replace ‘stat’ with ‘hp’, ‘mp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. Include ‘show’ and it will show the target getting the buff removed in the battle log.

Usage Example: 

	remove atk buff: user, show
	remove def buff: target

#### REMOVE stat DEBUFF: target, (show)

Removes the ‘stat’ debuff from target. Replace ‘stat’ with ‘hp’, ‘mp’, ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, or ‘luk’. Include ‘show’ and it will show the target getting the debuff removed in the battle log.

Usage Example: 

	remove atk debuff: user, show
	remove def debuff: target

#### REMOVE STATE X: target (show)
#### REMOVE STATE X, Y, Z: target (show)

Removes X state (including Y and Z if used in that format) from target. If ‘show’ is included, it will display any state related messages.

Usage Example: 

	remove state 5: target
	remove state 6, 7, 8: user, show

#### SE: filename, (volume), (pitch), (pan)
#### SE: PLAY OK
#### SE: PLAY CURSOR
#### SE: PLAY CANCEL
#### SE: PLAY BUZZER
#### SE: PLAY EQUIP
#### SE: PLAY SAVE
#### SE: PLAY LOAD
#### SE: PLAY BATTLE START
#### SE: PLAY ESCAPE
#### SE: PLAY ENEMY ATTACK
#### SE: PLAY ENEMY DAMAGE
#### SE: PLAY ENEMY COLLAPSE
#### SE: PLAY BOSS COLLAPSE 1
#### SE: PLAY BOSS COLLAPSE 2
#### SE: PLAY ACTOR DAMAGE
#### SE: PLAY ACTOR COLLAPSE
#### SE: PLAY RECOVERY
#### SE: PLAY MISS
#### SE: PLAY EVASION
#### SE: PLAY MAGIC EVASION
#### SE: PLAY REFLECTION
#### SE: PLAY SHOP
#### SE: PLAY USE ITEM
#### SE: PLAY USE SKILL

Causes the battle to play a Sound Effect. If you choose a filename (without the filename extensions), the game will play that ME instead. Using this option opens up access to the volume, pitch, and pan control, all of which are optional to use. If no values are inputed for volume, pitch, and pan, the game will use the settings in this plugin’s parameters. Using the action sequences with ‘play x’ in them will cause the game to play a system sound set within RPG Maker’s database.

Usage Example: 

	se: play enemy attack
	se: Ice1
	se: Laser2, 80, 100, 0

#### TP +X: target, (show)
#### TP -X: target, (show)
#### TP +X%: target, (show)
#### TP -X%: target, (show)
#### TP +VARIABLE X: target, (show)
#### TP -VARIABLE X: target, (show)
#### TP +VARIABLE X%: target, (show)
#### TP -VARIABLE X%: target, (show)

Target(s) gains TP equal to X values. To show the popup, insert ‘show’ after the target in the action sequence line. Including ‘show’ is entirely optional. If ‘show’ is omitted, no popup will be displayed. For TP to actually show popups, another plugin is needed to display TP popups.

Usage Example: 

	tp +500: user
	tp -variable 5: target
	tp +25%: target
	tp -variable 7: user

***

### Happy RPG Making!
