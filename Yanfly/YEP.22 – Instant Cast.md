##YEP.22 – Instant Cast
A popular request from the RPG Maker VX and Ace versions of Yanfly Engine, Instant Cast makes its way into RPG Maker MV’s plugin library with a few more features now! Instant Cast allows for skills and items to be instantly used after being selected without using up the user’s turn!

来自RPG Maker VX 和VX ACE软件的非常受欢迎的需求。立即释放带给MV插件很多特点。立即释放允许技能或者物品可以立即使用而不需要浪费玩家回合

***
###Introduction
***
When an action has an instant cast property, that action is used immediately on the spot without needing to wait for the turn to start. After using it, the actor can perform another action. This can add a whole new dimension of battle depth to your game as instant cast actions do not consume a turn. Note that if your actors can perform multiple actions, the instant cast will only occur if it is the very first action selected and not a subsequent one.

当行动拥有立即释放特性时，这个行动将会在这个点立即使用而不用等待回合来开始。使用完后，玩家可以继续使用其他行动。这就可以让你的战斗更加有深度。如果你的角色有多个行动，立即释放这个行动必须是第一个技能并且不在战斗序列内。

In the event an enemy uses an instant cast skill, once the enemy’s turn comes up, it will perform the instant cast skill and then immediately after, perform another skill.

在事件中，如果敌方使用立即释放技能，一旦敌方回合开始，它会立即释放并且之后开始其他技能

It is highly recommended to use this plugin with another plugin that enables skill restrictions.

这个插件通常用来开启技能限制

***
###Notetags
***

The following are some notetags you can use to apply Instant Cast properties to your actions.

下面标签你可以用来设置立即释放特性

####Skill and Item Notetags:
	<Instant>
	<Instant Cast>
Both notetags work the same. This causes this action when selected as the first action for an actor to be instantly cast. When used by an enemy, this will cause the enemy to have a follow up action without consuming the enemy’s turn.

这2个标签是一样的。可以让第一个行动使用时是立即释放，当敌方使用时，这将会让敌方可以继续开始下一个行动。

####Actor, Class, Enemy, Weapon, Armor, and State Notetags:
	<Instant Skill: x>
	<Instant Skill: x, x, x>
	<Instant Skill: x to y>
This makes skill(s) x into having instant cast properties for the actor, class, enemy, or whenever the weapon or armor is equipped, or whenever the state is applied. If using ‘x to y’, it will be applied to all the skills from x to y.

如果特定角色、敌方、职业或者装备特点武器等，甚至特点状态，这个技能就会被立即释放

	<Instant Item: x>
	<Instant Item: x, x, x>
	<Instant Item: x to y>
This makes item(s) x into having instant cast properties for the actor, class, enemy, or whenever the weapon or armor is equipped, or whenever the state is applied. If using ‘x to y’, it will be applied to all the items from x to y.

如果特定角色、敌方、职业或者装备特点武器等，甚至特点状态，这个物品使用就会被立即释放

	<Cancel Instant Skill: x>
	<Cancel Instant Skill: x, x, x>
	<Cancel Instant Skill: x to y>
This makes skill(s) x unable to be instantly cast. This will take priority over all other properties that may influence instant casting if the actor, class, enemy, equipment, or states possess this notetag. If using ‘x to y’ then it will be applied to all skills from x to y.

如果特定角色、敌方、职业或者装备特点武器等，甚至特点状态，这个技能立即释放特性被取消

<Cancel Instant Item: x>
<Cancel Instant Item: x, x, x>
<Cancel Instant item: x to y>
This makes item(s) x unable to be instantly cast. This will take priority over all other properties that may influence instant casting if the actor, class, enemy, equipment, or states possess this notetag. If using ‘x to y’ then it will be applied to all items from x to y.

如果特定角色、敌方、职业或者装备特点武器等，甚至特点状态，这个物品立即释放特性被取消

***
###Happy RPG Making!

