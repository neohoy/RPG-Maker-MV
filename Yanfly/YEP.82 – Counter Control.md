##YEP.82 – Counter Control
***
###Introduction
***

This plugin requires YEP_BattleEngineCore. Make sure this plugin is located under YEP_BattleEngineCore in the plugin list.

这个插件需要 YEP_BattleEngineCore。确保他放在 YEP_BattleEngineCore下面

If you are using Imported.YEP_X_BattleSysATB or Imported.YEP_X_BattleSysCTB, place this plugin under those plugins in the plugin list.

如果你使用了YEP_X_BattleSysATB或者YEP_X_BattleSysCTB，请放在他们下面

The default counterattack trait in RPG Maker MV doesn’t give many options for the developer. It’s a skill that flatout cancels out the physical skill of the attacker by evading it and then producing a normal attack from the counterattacker. This plugin will give you more control over how counters work in the sense that you can choose to have the counter connect first before allowing the counter skill to proc.

默认的反击特性没有太多开发设置。这是一个可以躲避敌方攻击并且反击的技能。这个插件可以让你更好的控制反击方式。
***
###Instructions – How Advanced Counters Work
***
A counterattack is an action that serves as a reaction to an action used by an opposing battler unless the action is marked as able of being countered by allied members.

反击是作为对一项行动的反馈行动。

Now begins a clash between the attacker’s anti-counter stat (newly added) against the target’s counter stat plus any of the action’s modifiers. Once the finalized counter rate is decided, a random number check is made to see if the counter will pass. If it doesn’t, no counter will occur. If it does, the next step occurs.

当判断反击成功时，才会行动

The target will then generate a pool of skills it can use as counters. It will go in a priority list mentioned in the next section below. The battle system will then go through the pool of skills in order and select the first counter skill that meets all of the conditions required. If no skill is selected, no skill will be used as a counter. All skills have a mandatory requirement of being able to pay the skill’s cost and can use it.

将会从反击技能池选择技能进行反击

Once the skill is selected, the counter skill is placed in the counter queue and waits for the current attacker’s turn to be over. Once over, the actions in the counter queue will begin. The counterattacker will perform counter actions without conflicting with their own turns. This process will repeat itself until the counter queue is emptied.

技能选择会，将会进入反击队列。

During the counter queue process, counter skills can trigger counter skills, too. For that reason, there is a maximum queue size determined by the plugin parameters. Once the queue count reaches this size, no more counter skills will be added to the counter queue.

反击也可以诱发反击，你可以设置最大值

***
###Instructions – Counter Skill Priority List
***

When the pool of counter skills is being generated, they will be generated in the following order:

1. States – Highest Priority Notebox
2. States – Lowest Priority Notebox
3. Equipment – Weapons Notebox
4. Equipment – Armors Notebox
5. Actor – Current Class Notebox
6. Actor – Actor Notebox
7. Enemy – Enemy Notebox

The order of the pool of counter skills matter in that when going through the conditions of the counter skill to be used, the first counter skill whose condition is met will be the ne used.

技能池产生后，执行顺序如下：  

1、2.从高优先度的状态到低优先度状态  
3. 武器标签  
4. 装备标签  
5. 职业标签  
6. 角色标签  
7. 敌人标签

***
###Notetags
***

You can use the following notetags to alter counters in your game. Each of these notetags will alter counters in a particular way.

使用下面标签设置

####Actor and Enemy Notetags:

	<Default Counter: x>
	<Default Counter: name>
Sets the default counter skill to x. If it is left as 0, then the counter skill will be RPG Maker MV’s default counter skill. If you are using the name of the skill, and there are multiple skills in the database with the same name, then priority will be given to the skill with the highest ID. *Note: Use 0 for x if you wish to add RPG Maker MV’s default counter.

默认反击技能

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:

	<Counter Skills: x>
	<Counter Skills: x, x, x>
	<Counter Skills: x to y>
This will add to the list of possible counter skills for the battler. If multiple skill ID’s are listed, then they’re all added. Priority will be given to the counter skills listed earlier.
Note: Use 0 for x if you wish to add RPG Maker MV’s default counter.  
Note2: See the Counter List priority to see which skills will be given priority on the counter skill list.  

反击技能表

	<Counter Skill: name>
This will add the named skill to the list of possible counter skills for the battler. If there are multiple skills in the database with the same name, then priority will be given to the skill with the highest ID.
Note: See the Counter List priority to see which skills will be given priority on the counter skill list.

反击技能表

	<Counter Total: +x>
	<Counter Total: -x>
Alters the number of times the battler can counter by x. This is the amount of times the battler can counter until the battler’s turn comes up at which, the number of times is reset.

反击次数

	<Target Counter: x%>
When this battler attacks an opponent target, this will cause the target counter rate to be altered by x% rate. If a target has 10% CNT, then a notetag of 50% will cause the counter rate to become 5%.

目标反击率

	<Target Counter: +x%>
	<Target Counter: -x%>
When this battler attacks an opponent target, this will cause the target counter rate to increase or decrease by x%. If a target has 10% CNT, then a notetag of +50% will cause the counter rate to become +60%.

目标反击率

	<Evade Counter>
This will change all counter skills used by the related battler to become evade counters regardless of their default nature. However, if the battler is affected by a trait that is <Hit Counter>, then priority will be given to the <Hit Counter> trait instead.

躲避反击

	<Hit Counter>
This will change all counter skills used by the related battler to become hit counters regardless of their default nature. If the battler is also affected by <Evade Counter>, this effect will take priority.

伤害反击

####Skill and Item Notetags:

	<Ally Counter>
Makes this action able to proc counter skills by allied members.

可以被队员用来反击

	<Ally Cannot Counter>
Makes this action unable to proc counter skills by allied members.

不可以被队员用来反击

	<Cannot Counter>
Causes this action to be un-counterable. This means that it will always return a 0% counterattack possibility.

不能反击

	<Counter Rate: x%>
This will cause this action to proc a counter from the target by x% rate. This means if the target has a 10% chance to counter and this notetag is 50%, then the target will have a 5% chance to counter.

反击概率

	<Counter Rate: +x%>
	<Counter Rate: -x%>
This will cause this action to proc a counter from the target by an additive x%. This means if the target has a 10% chance to counter and this notetag is +50%, then the target has a 60% chance to counter.

反击概率

####Skill Notetags:

	<Evade Counter>
If this skill is being used as the counter skill, the battler will evade the current action and then counter.

躲避后反击

	<Hit Counter>
If this skill is being used as the counter skill, the battler will take the hit against the current action and then counter.

伤害后反击

	<Counter Name: text>
This changes the displayed name of the skill when used as a counter skill to ‘text’.

反击技能名

	<Counter Icon: x>
This changes the displayed icon of the skill when used as a counter skill to x icon.

反击技能图标

***
###Notetags – Counter Conditions
***

When making your counter skills, you can have those counter skills respond only to specific conditions. If all conditions are met, the counter skill will occur. If a single condition isn’t met, that counter skill will then be skipped and the next one will be checked. To add counter conditions, use the following notetags:

设置反击条件

####Skill Notetags:

	<Counter Condition>
	condition
	condition
	</Counter Condition>
	
Replace the ‘condition’ text in between the notetags with the listed in the conditions list below to best fit what you want.

— Example —

	<Counter Condition>
	physical hit
	single target
	</Counter Condition>
This skill will only be used as a counter skill if the current action is a physical hit that’s single target.

单一目标物理伤害后反击

***
###Happy RPG Making!


