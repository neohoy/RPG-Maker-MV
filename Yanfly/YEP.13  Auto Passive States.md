##YEP.13 – Auto Passive States
Add passive states to your game! They can be innate to actors, classes, appear when a piece of equipment is worn, or after an actor learns a skill! Having a passive state increase gameplay depth by a lot!

为你的游戏添加被动状态。当角色装备武器或者学习技能时，可以获得一个永久的状态。为你的游戏添加被动状态提高游戏可玩性吧！

***
###Introduction
***

Passive states are states that are automatically active. You can think of them as an extension of traits but with more flexibility. They will always be there as long as the actor or enemy has auto passive state notetags.

被动状态是自动添加的。你可以认为他们是更加灵活的拓展特性。只要角色有状态标签，那么就会一直存在状态。

> NOTE: For those using Passive States with your skills, the passive states will only be applied from Learned Skills! They will not be applied from skills that are learned through traits. Why? Because without this restriction, a passive skill that applies a passive state that in turn provides a skill through its traits will cause an infinite loop in your game and cause it crash. So if you want your skills to provide a passive state, have your actors learn the skill instead of applying it through a trait.  
> 注意：对于有被动状态的技能，只有学习的时候会被应用。通过特性获得的技能不会造成被动状态。为什么呢？因为如果没有这个限制，被动技能执行被动状态将会让你的游戏进入一个无限循环而造成崩溃。所以如果你希望你的技能提高被动状态，让你的角色去主动学习这个技能而不是通过特性获得。

***
###Notetags
***

####Actor, Class, Skills, Weapon, Armor, Enemy Notetags:
	<Passive State: x>
	<Passive State: x, x, x>
This will allow the actor or enemy to have state x as a passive state. If placed inside a weapon or armor notebox, the user will have that passive state.

允许你的角色获得被动状态x。你可以放在角色、敌方、武器、装备等标签栏

	<Passive State: x to y>
This will add the states x through y (in a sequence) for the actor or enemy to have as a passive state. If placed inside a weapon or armor notebox, the user will have that passive state.

让你的角色获得状态x到y。你可以放在角色、敌方、武器、装备等标签栏

####State Notetags:
	<Passive Condition: HP Above x%>
	<Passive Condition: HP Below x%>
	<Passive Condition: MP Above x%>
	<Passive Condition: MP Below x%>
If the user’s HP or MP is above/below x% of the MaxHP or MaxMP, this condition will be met for the passive state to appear.

当血量或者魔法量低于或者高于最大值时，被动状态触发。

	<Passive Condition: Stat Above x>
	<Passive Condition: Stat Below x>
Replace ‘stat’ with ‘HP’, ‘MP’, ‘TP’, ‘MAXHP’, ‘MAXMP’, ‘ATK’, ‘DEF’, ‘MAT’, ‘MDF’, ‘AGI’, ‘LUK’. If the above stat is above/below x, then the condition is met for the passive state to appear.

当其他状态低于或者高于x时，被动状态触发

	<Passive Condition: Switch x ON>
	<Passive Condition: Switch x OFF>
If switch x is either ON/OFF, then the condition is met for the passive state to appear.

当开关是开启或者关闭时，被动状态触发

	<Passive Condition: Variable x Above y>
	<Passive Condition: Variable x Below y>
Replace x with the variable you wish to check to see if it’s above/below y, then the condition is met for the passive state to appear.

当变量x高于或者低于y时，被动状态触发

***
###Lunatic Mode – Conditional Passives
***

For those who understand a bit of JavaScript and would like for their passive states to appear under specific conditions, you can use this notetag to accomplish conditional factors.

对于掌握JS语言并且想把被动状态用于特殊情况时，你可以使用下面的标签来完成。

####State Notetags:
	<Custom Passive Condition>
	if (user.hp / user.mhp <= 0.25) {
	condition = true;
	} else {
	condition = false;
	}
	</Custom Passive Condition>
This enables you to input conditions to be met in order for the passive state to appear. If the ‘condition’ variable returns true, the passive state will appear. If the ‘condition’ returns false, it won’t appear. If condition is not defined, it will return true and the passive state will appear on the battler.

这可以使你选择特定情况来让被动状态出现。如果condition返回为true，这个被动状态就会出现。如果condition返回为false，这个被动状态就不会出现。如果condition没有定义，这个被动状态会出现。

Note: All non-custom passive conditions must be met before this one can be fulfilled and allow the custom condition to appear.

注意：所有非自定义情况会在这个完成之前运行，并且允许自定义情况出现

***
###Happy RPG Making!

