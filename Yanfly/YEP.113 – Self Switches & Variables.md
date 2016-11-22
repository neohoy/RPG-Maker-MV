##YEP.113 – Self Switches & Variables

##Introduction

RPG Maker MV comes with Self Switch functionality. However, the number of Self Switches provided is a mere 4 in total, not enough for some of the more complex events. This plugin will let you extend the number of Self Switches. Self Variables, on the other hand, do not exist in RPG Maker MV, so this plugin will provide functionality for that as well.

RPG Maker MV拥有独立开关功能。可是，独立开关仅仅提供了4个，对于许多复杂的事件并不够用。这个插件可以让你拓展独立开关的数量。独立变量实际上并不存在，因此这个插件提供了类似的功能

##Instructions

In order to set up your custom Self Switches and Self Variables, you must first do a few things.

为了设置自定义独立开关和变量，你需要先做下面的几件事

1. Open up your Switches/Variables list in the editor.
2. Name the Switch to have ‘Self Sw’ in its name.
– or –
Name the Variable to have ‘Self Var’ in its name.

1.打开你的开关和变量编辑器  
2.在开关前面加‘Self Sw’，在变量前面加 ‘Self Var’

Now, any time you use these following event commands, if the Self Switch or Self Variable is the focus, it will be used instead of the actual Switch or actual variable:

现在你可以使用下面的事件命令了，如果独立开关和变量被强制打开，那么他会替代之前的开关和变量
<pre>
Self Switches:
– Control Switches
– Conditional Branch
– Set Movement Route (Switch ON/Switch Off)

Self Variables:
– Show Text (using the \v[x] codes)
– Input Number
– Select Item
– Control Variables
– Conditional Branch
– Change Gold
– Change Items
– Change Weapons
– Change Armors
– Change HP
– Change MP
– Change TP
– Recover All
– Change EXP
– Change Level
– Change Parameter
– Change Skill
– Change Equipment
– Change Enemy HP
– Change Enemy MP
– Change Enemy TP
</pre>
Note that not all plugins that use variables will be necessarily compatible with the custom made Self Switches and Self Variables. Of the YEP library, these plugins are compatible with this plugin:

注意不是所有的插件使用都可以适配自定义开关和变量，下面是YEP插件里面可以适配的

	– YEP_EventMiniLabel
	– YEP_MapSelectSkill

Non-Yanfly Engine Plugins may or may not be compatible.

非Yanfly引擎的插件可能适配也可能不适配

###Plugin Commands

Those who would like to remotely control Self Switches and Self Variables can use the following plugin commands:

想微调独立开关和变量的可以使用下面的插件命令

####Plugin Commands:

	SelfSwitch Map x, Event y, Switch z to true
	SelfSwitch Map x, Event y, Switch z to false
	SelfSwitch Map x, Event y, Switch z to code
– This will change the Self Switch used for map ‘x’, event ‘y’, and switch ‘z’ to the value of ‘code’ value. You can replace ‘code’ with a ‘true’ or ‘false’ value or a piece of code like `‘$gameSwitches.value(4)’`.

这会改变独立开关z在地图x，事件y里面的值

	SelfVariable Map x, Event y, Variable z to 12345
	SelfVariable Map x, Event y, Variable z to value + 100
	SelfVariable Map x, Event y, Variable z to code
– This will change the Self Variable used for map ‘x’, event ‘y’, and switch ‘z’ to the value of ‘code’ value. You can replace ‘code’ with a number like ‘12345’, a calculation using ‘value’ (the current value of the Self Variable), or a piece of code like `‘$gameVariables.value(4)’`.

这会改变独立变量z在地图x，事件y里面的值

###Lunatic Mode – Script Calls

For those who’d rather deal altering self switches and/or self variables inside of the script call event instead, you can use these script calls:

对于那些想要从代码里改变独立开关和变量值得人，可以使用下面的脚本命令

####Script Call:

	this.getSelfSwitchValue(mapId, eventId, switchId)
– Replace mapId with the map ID the event exists on. Replace eventId with the ID of the event. And replace the switchId with the ID of the switch. This will get the true/false value of that event’s self switch.

获得独立开关值

	this.getSelfVariableValue(mapId, eventId, varId)
– Replace mapId with the map ID the event exists on. Replace eventId with the ID of the event. And replace the varId with the ID of the variable. This will get the value of that event’s self variable.

获得独立变量值

	this.setSelfSwitchValue(mapId, eventId, switchId, true)
	this.setSelfSwitchValue(mapId, eventId, switchId, false)
– Replace mapId with the map ID the event exists on. Replace eventId with the ID of the event. And replace the switchId with the ID of the switch. This will set that self switch to true or false.

打开或者关闭独立开关

	this.getSelfVariableValue(mapId, eventId, varId, value)
– Replace mapId with the map ID the event exists on. Replace eventId with the ID of the event. And replace the varId with the ID of the variable. This will set that self variable to the value inserted.

设置独立变量的值

###Happy RPG Making!