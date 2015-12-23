## YEP.3 – Battle Engine Core
The default battle system for RPG Maker MV now allows for the ever so popular side-view! However, we can beef it up a little bit more using the Battle Engine Core to add more features and capabilities to the battle system!

RPG Maker MV默认的战斗系统已经支持流行的横版战斗，我们可以使用战斗核心引擎来增加更多的特点和能力

***
### Introduction
***

This plugin alters the various aspects of the default battle system, allowing it to be more streamlined like most modern RPG’s and less clunky like older RPG’s. This ranges from choosing what text will appear in the battle log window at the top and how it will be displayed.

这个插件改变了战斗系统的很多方面，使其看起来更像现代的角色扮演游戏，而不是过时笨重的那种。这改变了战斗界面的文本的显示以及出现方式。

***
### Battle Messages
***

When changing “Terms” and the “Messages” that appear in battle, inserting the following tag anywhere in the message will cause the message to center itself in the battle log.

当改变了战斗过程中的选项和信息时候，插入下面的标签就可以让信息在战斗记录里居中

	<CENTER>
	
> This tag must be all caps in order for the battle log window to recognize it as an instruction to center the displayed battle text message.

> 这个标签可以覆盖所有的战斗记录窗口，并且将视为一种居中战斗文本信息的指令。

***
### Battle Windows
***

There’s various options to adjust the window settings found in the battle system to make navigating the battle system more intuitive. Such options include starting the turns with the Actor Command Window instead of the Party Command Window (the Fight/Escape Window). The Party Command Window is still accessible but only by pressing cancel on the first actor’s window.

为了使战斗系统的导航更加简便，这里有很多选项来调整战斗系统的角色窗口之后出现。

***
### Battle Order
***

The battle turn order is also fixed, too. This way, any battlers that have their AGI value changed over the course of battle will reflect those changes during the current turn rather than the following turn. The action speed calculation can also be adjusted and finetuned to have the random factor of its speed calculation formula removed, too, making AGI actually worthwhile as a tactical parameter.

这个战斗回合系统也被修复，这样，任何有敏捷值改变的情况的战斗，将会在当前回合生效而不是下个回合。行动速度计算也被调整过，移除了过去速度计算公式带有随机的因素，让敏捷值可以更加实际的作为一个战术上的因素。

***
### Multiple Hits
***

Multi-hit action will no longer end prematurely if the target dies midway through the action. This is done through toggling immortal states. To make use of feature, make sure your database has an Immortal State somewhere. If you do not wish to use this feature, set the Parameter for Immortal State ID to 0 instead.

如果伤害标签在行动中消失，多重伤害系统不会中断。这个通过切换永久状态来实现的。如果要使用这个特性，请确保数据库中存在一个永久状态；如果不想使用，请将永久状态参数ID改为0。

***
### Popup Revamp
***

Although the damage popups may still look the same as the default ones from MV, the process in which they’re created is now different to streamline the damage popup process. Before, popups would only appear one a time with a frame’s different at minimum in order for them to show. Now, any actions that occur at the same frame will now all show popups at the same frame, making for smoother and less clunky damage popups.

尽管伤害数值的弹出系统和原版MV看起来一样，但是他们的进程是完全不同的。在之前，弹出系统在1帧只会弹出一次，但现在，我们可以在同1帧显示所有伤害，这使其看起来更加平滑。

***
### Common Events
***

Common Events will now occur at the end of each action regardless of whether or not the enemy party is still alive. With proper placing of the action sequence tags, you can make the skill’s common event occur in the middle of an action, too. However, keep in mind if you force an action in the middle of another action, the remainder of the former action’s sequence list will become null and void in favor of the new forced action.

无论敌人队伍是否存活，公共事件将会在每次行动结束的时候执行，通过恰当的放置行动序列标签，你可以让技能的公共事件在一个行动当中执行。但是，请注意如果你让一个行动在另一个行动当中执行，剩余的行动序列将会变成空的来取代新的行动。

***
### Casting Animations
***

Casting Animations help provide visual hints for players either by letting them know which battler is going to perform an action or what type of skill that action will be. This plugin enables skills to have casting animations that can be modified universally or customized for each individual skill.

角色动作将会协助提供给玩家，让他们明白战斗者是谁，以及技能使用类型。这个插件可以让技能拥有动作，这些动作是可以为单独技能自定调整的

**Skill Notetag:**

	<Cast Animation: x>

> Sets the skill’s cast animation to animation ID x. Setting x to zero will cause the skill to not have any animaton at all.

> 设置技能动作ID，设置0将会取消动作

***
### Changing Battle Systems
***

While the player is not in battle, you can change the battle system using a Plugin Command. With only this plugin, there is only one battle system included: the default battle system.

当玩家不在战斗时，你可以通过插件命令改变战斗系统。如果只使用这个插件，这里只包含了默认的战斗系统

**Plugin Command:**

	setBattleSys DTB
	
> Sets battle system to Default Turn Battle.

> 设置战斗为默认回合制

Other future plugins may include other battle systems that may utilize the Battle Engine Core.

未来其他插件将会包含其他战斗系统

***
### Sideview Actions
***

In RPG Maker MV’s default battle system, both the sideview and the frontview settings do not display counterattacks, reflected magic attacks, nor any case of substituting for battle members. The Battle Engine Core provides games that are using the sideview settings small amounts of animations to relay information to the player in a more visual sense.

在软件默认的战斗系统里，竖向和横向的战斗方式都没有显示反击，显示魔法攻击，或者任何战斗者的替换队员。这个战斗系统核心引擎可以提供给横版战斗模式的游戏更好的战斗队员显示效果。

Magic Reflection will also display a reflection animation to indicate the battler has reflection properties. This animation can be changed in the parameters, but certain actors, classes, enemies, weapons, armors, and states can display a unique kind of animation for reflection if desired.

魔法攻击也将会显示一个相应的动画，来告诉玩家已经准备好战斗。这个动画可以用参数改变，但是角色，职业，敌人，武器，装备和状态可以根据需要显示独有的动画。

**Actor, Class, Enemy, Weapon, Armor, and State Notetag:**

	<Reflect Animation ID: x>
	
> Changes the user’s reflect animation to x. This will take priority in the following order: Actor, Class, Enemy, Weapon, Armor, State, Default.

>改变角色的动画为X。这将影响角色，职业，敌人，武器，装备及状态等等

Sometimes, you don’t want your enemies to be able to move. Or you don’t want certain actors to be able to move. They’re just stationary for whatever reason. To accomplish that, you can use this notetag to forbid the battler from moving.

有时，你不希望你的敌人可以移动，或者你不希望某个角色移动。他们只是固定的。为了完成这件事，你可以使用下面这个标签禁止参与战斗者移动。

**Actor, Class, Enemy, Weapon, Armor, and State Notetag:**

	<Sprite Cannot Move>
	
> Prevents the battler’s sprite from moving. This will take priority in the following order: Actor, Class, Enemy, Weapon, Armor, and State. If an enemy is unable to move when it performs an action, it will flash white as if it normally does in front view.

> 阻止了参与战斗者移动。这将影响角色，职业，敌人，武器，装备及状态等等。如果敌人在其行动的时候不能移动，他将会像竖版战斗那样闪烁。


***
### Custom Sideview Battler Anchor
****

Sideview battlers are generally centered horizontally, and grounded at their feet. However, not all sideview battler spritesheets work this way. In the event you have a sideview battler that doesn’t conform to those standards, you can ‘anchor’ them a different way.

横向战斗时，角色图通常被置于中间，并且固定在脚部，而不是所有的横版战斗都会这样。用这个事件，对于那些不遵从标准的角色，我们可以用不同的手段固定他们。

**Actor Notetags:**

	<Anchor X: y.z>
	<Anchor Y: y.z>
	
> This sets the anchor location for the actor’s sideview battler at y.z. By default, the X anchor is 0.5 while the Y anchor is 1.0. If you want the X anchor to be a bit more to the left, make it less than 0.5. Make it more than 0.5 to make the X anchor more towards the right. To raise the Y anchor, set the number value to less than 1.0. Keep adjusting until you find that perfect anchor setting.

> 这个设置了角色横向战斗时，侧视图的位置。系统默认值中，X=0.5,Y=1.0。如果你希望X可以向左一点，你需要设置它小于5.或者设置大于5来使其向右。为了提高Y方向，你需要设置小于1.0的值。请不断调整直到你完成了最正确的设置。

***

### Happy RPG Making!
