##YEP.16 – Battle A.I. Core

Tired of dumb enemies that turn your otherwise challenging game into an easy-peasy walk in the park? The Battle A.I. Core plugin allows you to manually adjust the settings and patterns of your enemies so that they can deliver MANLY poundings onto your players.

是否厌倦了在地图上轻松的走动，随意的虐怪。这个插件可以让你调整敌方设置

***
###Introduction
***

RPG Maker MV’s default enemy AI is a bit lackluster even if you managed to have it based completely on the rates and switches. There is no way to control the way the enemy chooses targets by default, nor are the conditions imposed by the default editor enough to satisfy the majority of checks. This plugin enables you to set a priority list of conditions, actions, and the targets selected for the enemy to go through before making a decision on how to participate in battle.

MV默认的敌方智能有些枯燥，即便你想利用概率和开关来改变他们。这里没法控制敌方攻击目标。这个插件可以让你设置一个条件优先列表。

These conditions contain all of the default editor’s conditions plus more, such as determining the parameter values of a target, whether or not a state exists on a target, the target’s elemental weakness (or resistances), and more before deciding an action. Furthermore, you can set an AI level for the enemies to make them more consistent in the way they go about fighting your players or more random in the way the enemies treat the priority list, too.

这些条件包括默认条件，就像目标的状态参数，或者元素等等。你甚至可以设置敌方智能等级，让其战斗更加随机有趣

***
###Parameters
***

Dynamic Actions		
By default, the enemy’s actions are determined at the start of the turn. While this works in its own right, enabling Dynamic Actions allow enemies to make a decision when the enemy’s turn comes up instead. This prompts enemies to be more flexible and to appear more intelligent in battle, thus, giving your players a bit more of a challenge.

伤害行动：开启时，敌方将会更加灵活

Element Testing  
If this is disabled, enemies will automatically know the elemental weakness, resistance, etc. about all actors. If enabled, enemies will need to test out the skills on various actors first before making a decision. Until the enemy learns about the actor’s elemental rates, the enemy is always willing to try using the skill on the target actor. However, if the skill itself does not possess an element, then no information will be registered. All elemental data is reset at the start of each battle for all enemy parties.

元素测试：关闭时，敌方会自动了解我方元素抵抗情况。如果开启，则需要利用技能测试。如果敌方掌握了玩家的元素信息，将会用技能作用玩家。

Default AI Level  
Not all enemies are intelligent. In fact, some of them are dumb or random. Setting the AI Level of a foe at a low number means the foe is more random while a higher AI Level foe is more consistent. How the AI Level works is, a random number will be checked from 0 to 99. If that enemy’s AI Level is higher than that number, that action is checked to see if the condition is fulfilled or not. If the AI Level is lower than that number, the condition is automatically deemed false and continues on to the next action. The check is ran each time a new action is checked upon. This random factor is only applied to <AI Priority> lists and do not apply to default actions.

默认智能等级：不是所有敌方都是智能的。如果等级较低，就意味着敌方行为更加随机，而相反则更加固定。如果如果敌方智能等级高于默认值，则行动会检查条件状态，如果没有则不会。

***
###Enemy AI Level
***
Enemy AI levels do not determine how difficult they are. Instead, they determine how strictly they will follow the <AI Priority> lists. An AI Level of 80 means it has an 80% chance of following the prioritized action on the AI Priority list before moving onto the next one where there will be another 80% chance and so on. If the AI level is lower, the chance is lower, making the AI to be more random.

敌方智能等级：这决定这敌方困难程度。80级的智能意味着将会80%的几率执行智能行动。

####Enemy Notetag:
	<AI Level: x>
Sets the enemy’s AI level to x. The lower x, the more random the enemy. The higher for x, the more strict the enemy is about following the AI Priority list found in its notebox, too.

设置敌方智能等级

***
###Enemy AI Priority
***
If an enemy has an AI Priority list, the enemy will go down that list from top to bottom (giving the actions at the top more priority than the ones at the bottom) looking for any actions whose conditions are fulfilled. If that condition is fulfilled, then that action will be the action the enemy will partake in.

如果设置了敌方智能优先执行列表，将会从上到下检索。

To set up a Priority List for the enemy, you must place inside the enemy’s notebox notetags that match the following format:

你需要用下面标签来设置优先列表

	<AI Priority>
	condition: SKILL x, target
	condition: SKILL x, target
	</AI Priority>

	<AI Priority>
	condition: skill name, target
	condition: skill name, target
	</AI Priority>
Any number of conditions and skills can be placed in between the two <AI Priority> tags. You can choose to use skill ID’s or the skill names. However, if you use the skill names, keep in mind that it is not case sensitive and if any skills in your database have matching names, the skill with the larger skill ID will be the action used.

你可以在里面放置多个条件。

***
###Conditions
***

The following is a list of ways you can format your conditions for the enemy to choose the right skill. In addition to deciding whether or not the skill will be used, the condition also selects the enemy target. The following list will tell you how the conditions are met and what targets will be selected for battle.


下面这个列表你可以用来参考作为你的条件。

####ALWAYS

This condition will always be fulfilled. The valid target group is all targets within scope.

条件总是满足

Example: 

	Always: Skill 10, Lowest HP%

####ELEMENT X case

This allows you to match the element rate of element X (use either a number or the name of the element in place of ‘X’) to see whether or not the conditions for the action are fulfilled. Replace ‘case’ with ‘Neutral’ for normal element rate, ‘Weakness’ for anything above 100% element rate, ‘Resistant’ for below 100% element rate, ‘Null’ for 0% element rate, and ‘Absorb’ for below 0% element rate. Valid targets will be those with the matching element rates.

允许你设置元素情况，例如中立，虚弱，抵抗，无等

Example: 

	Element Fire Weakness: Fireball, Lowest HP%
	Element Water Resistant: Water Cancel, Highest MAT
	Element 4 Null: Earthquake, Lowest MDF

####EVAL eval

This allows you to use any kind of code to check and fulfill a condition. This condition uses all alive members of the skill’s scope as valid targets.

你可以使用代码来设置条件

***
###Targeting
***

Targeting is optional but can be done via a small change to the condition. All you have to do is add a ‘,’ after the skill to indicate which target in the valid target group you would like to target. For example:

目标是可选的，你可以用逗号来添加多个目标

	Random 50%: Fire, Highest HP%

The condition to be met is the 50% random chance, but if it is fulfilled, the target selected will be the member on the targeting scope’s team with the highest HP percentage. When that happens, the ‘Fire’ skill will be used upon that target.

50%的概率，用火攻击生命百分比最高的

If no target is specified, a random target will be selected amongst the group of valid targets. Otherwise, refer to the following list:

如果目标没有特殊情况，将会随机选择，其他可参考列表

***
###Happy RPG Making!