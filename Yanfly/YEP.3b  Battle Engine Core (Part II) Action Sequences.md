## YEP.3b - Battle Engine Core (Part II) Action Sequences

***
### Action Sequences
***

The Yanfly Engine Plugins – Battle Engine Core includes the capability of using custom action sequences. Action sequences are basic instructions for the game to creating a customized skill both visually and mechanically. The Battle Engine Core, however, will only include the most basic of action sequences so the instructions on how to create a custom action sequence will be included in the Help file on future extension plugins for this plugin.
Adapted and improved from Battle Engine Melody, Action Sequences can now be used for the hardcore users of YEP’s Battle Engine Core. Using Action Sequences, you can create, animate, and alter the individual aspects of any battle action in the game.

战斗系统核心插件包含了自定义行动序列的功能。行动序列是对于游戏来说是非常基础的指令，可以从视觉和自动程度上创作自定义技能。战斗系统核心插件只包含最基础的行动序列，一次关于如何创作自定义技能的指南将会放在未来这个插件的拓展插件里面。兼容和提高了战斗系统插件，行动序列可以被战斗系统核心插件的骨灰级玩家使用。使用行动序列，你可以创造，制作动画，甚至变更游戏战斗行为的每一个方面。

***
### Action Sequences – ala Melody
***

Battle Engine Core includes Yanfly Engine Melody’s Battle Engine system, where each individual aspect of the skill and item effects can be controlled to a degree. These are called Action Sequences, where each command in the action sequence causes the game to perform a distinct individual action.

战斗系统核心插件包括Yanfly的序列战斗系统，这个系统可以改变角色的技能或者物品的各个方面。这些被称为动作序列，在动作序列中的每个命令都可导致游戏执行不同的动作。

Each skill and item consists of five different action sequences. They are as follows:

每一个技能和物品序列包含5个不同的行动，如下：

1. Setup Actions  
They prepare the active battler before carrying out the bulk of the action and its individual effects. Usually what you see here are things such as the active battler moving forward a bit, unsheathing their weapon, etc. This step will occur before the active battler expends their skill or item costs.  
准备动作  
这是执行众多行动和效果之前的准备动作。通常你会看到你的角色向前移动了一步，拔出武器等等。这步将发生在角色释放技能或者使用物品之前。

2. Whole Actions  
These actions will affect all of the targets simultaneously. Although this section does not need to be used, most actions will use this for displaying animations upon all enemies. This step occurs after skill and item costs.  
整体动作  
这个将会同时影响所有目标。尽管这个序列不是必须的，但是很多动作都会在这个阶段播放攻击动画。这步发生在释放技能和使用物品之后。

3. Target Actions  
This section will affect all of the targets individually. Used primarily for physical attacks that will deliver more personal forms of damage. Actions that occur here will not affect other targets unless specifically ordered to do so otherwise.  
目标动作
这步将会单独影响目标。主要放置更加具体的物理攻击效果。这里发生的动作将会不影响指定之外的其他目标。

4. Follow Actions  
This section will dedicate towards cleanup work after the individual targeting actions. Here, it’ll do things such as removing immortal flags, start up common events, and more.  
后续动作  
这部主要是在目标动作后的清理动作。这里将会移除增益效果，开始执行事件等等。

5. Finish Actions  
This section will have the active battler close up the action sequence. Usually stuff like running waits and holds at the last minute for skills and items, moving back to place, and others.  
结束动作  
这步将会关闭动作序列。通常是技能或者物品使用后的等待动作，以及角色退回原位置。

Now that you know each of the five steps each action sequence goes through, here’s the tags you can insert inside of skills and items. Pay attention to each tag name.

现在你知道了动作序列里的五步都是怎么运行的，这里是一些你可以插入技能或者物品里的表情。请注意每个标签的名字。

	<setup action>
	action list
	action list
	</setup action>
---

	<whole action>   
	action list    
	action list    
	</whole action>
---

	<target action>
	action list
	action list
	</target action>
---

	<follow action>
	action list
	action list
	</follow action>
---

	<finish action>
	action list
	action list
	</finish action>

They will do their own respective action sets. The methods to insert for the action list can be found below in the core of the Help Manual.

他们将执行相应序列的设定。这个列表可以在帮助手册的核心文件里找到。

Furthermore, to prevent overflooding every single one of your database item’s noteboxes with action sequence lists, there’s a shortcut you can take to copy all of the setup actions, whole actions, target actions, follow actions, and finish actions with just one line.

为了避免你要在每一个物品里面都要使用这个标签，你可以用这个简短的命令来负责你的标签，无论是准备动作，整体动作，目标动作，后续动作还是结束动作，都只需要一行。

	<action copy: x:y>
	
> Replace x with “item” or “skill” to set the type for the action list code to directly copy. The integer y is then the ID assigned for that particular object type. For example, to copy 45th skill’s action sequences, the code would be <action copy: skill:45> for anything that will accept these action codes. If you do use this notetag, it will take priority over any custom that you’ve placed in the notebox.

> 可以用物品或者技能来替代x,这样就可以直接负责标签命令。数字Y就是你要设定的特点主体的ID。例如，复制第45个技能行动序列。<action copy: skill:45>就可以完成。如果你要使用这个标签，请放在其他标签前面。

***
### Target Typing
***

You may notice that in some of the actions below will say “refer to target typing” which is this section right here. Here’s a quick run down on the various targets you may select.

你应该注意到那些参考目标类型。这里有一个参考目录。

译者认为：  

- 角色：即actor选项卡里的
- 敌人：即enemies选项卡里的
- 队员：不一定是actor里面的
- 对手：不一定是enemies里面的

user; This will select the active battler.  
使用者。当前选中的。  
target, targets; These will select the active targets in question.  
目标。被选中的目标。
actors, existing actors; These will select all living actors.  
角色。所有存活的角色。  
all actors; This will select all actors including dead ones.  
所有角色。包括死亡在内的所有角色。  
dead actors: This will select only dead actors.  
死亡角色。仅死亡的角色。  
actors not user; This will select all living actors except for the user.  
非使用者。存活且非使用者的角色。  
actor x; This will select the actor in slot x.  
角色x.选择角色X。
character x; This will select the specific character with actor ID x.  
队员x。选择队员x。  
enemies, existing enemies; This will select all living enemies.  
存活敌方。所有存活的敌方。  
all enemies; This will select all enemies, even dead.  
所有敌方。包括死亡在内的所有敌方。  
dead enemies: This will select only dead enemies.  
死亡敌方。仅死亡的敌方。  
enemies not user; This will select all enemies except for the user.  
非选中敌方。所有非选中的敌方。  
enemy x; This will select the enemy in slot x.  
敌方x。选择敌方x。  
friends; This will select the battler’s alive allies.  
队员。所有存活的队员。
all friends; This will select the all of battler’s allies, even dead.  
所有队员。包括死亡在内的所有队员。  
dead friends; This will select the battler’s dead allies.  
死亡队员。仅死亡的队员。  
friends not user; This will select the battler’s allies except itself.  
非使用者队员。非使用的队员。  
friend x: This will select the battler’s ally in slot x.  
队员x。选择队员x。  
opponents; This will select the battler’s alive opponents.  
存活对手。选择存活的对手。  
all opponents; This will select the all of the battler’s opponents.  
所有对手。所有的对手。  
dead opponents; This will select the battler’s dead opponents.  
死亡对手。所有死亡的对手。  
opponent x: This will select the battler’s opponent in slot x.  
对手x。选择对手x。  
all alive; Selects all living actors and enemies.  
所有存活者。所有角色和敌方的存活者。  
all members; Selects all living and dead actors and enemies.  
所有成员。所有存活或者死亡的角色和敌方。
all dead; Selects all dead actors and enemies.
所有死亡。所有死亡的角色和敌方。  
all not user; This will select all living battlers except user.  
非使用者。除了使用者的角色和敌方。  
focus; Selects the active battler and its targets.
焦点。选择战斗者和他的目标。
not focus; Selects everything but the active battler and its targets.
非焦点。除了战斗和他的目标外的所有。

***
### Action Sequences – Action List
***

The following contains a list of the actions you can use inside the five action sequences. Each action has a unique function and requires certain formats to operate properly.

下面这个列表包含了你可以在动作序列里执行的动作。每一个动作都有单独的功能并且需要明确的代码来开启。

***
#### ACTION ANIMATION
***

Plays the animation assigned to the skill/item. The animation will automatically select the skill’s/item’s assigned targets.

Usage Example: 

	action animation

播放技能或者物品动画。动画将会自动选择技能指定的对象。

***
#### ACTION COMMON EVENT
***

Plays the common event found within the skill’s/item’s traits list. This will only play the last common event on the list, following the game engine’s original process. Nothing else will continue on the action list until the common event is finished.

Usage Example: 

	action common event

执行技能或者物品内的公共事件。这个只会执行列表内最新的事件。在事件执行完之前没有其他的可以继续执行。

***
#### ACTION EFFECT: target
***

Causes the target(s) to take damage/healing from the skill/item and incurs any changes made to the target(s) such as buffs and states.

Usage Example: 

	action effect

通过技能或者物品造成伤害或者回复而产生的改变，比如增益效果等等。例如动作效果。

***
#### ANIMATION WAIT: X
***

Waits x animaiton frames. Each frame for an animation does not last one game frame, but instead, several. To make life easier, you can use this to have the game wait x frames played for the animation.

Usage Example: 

	animation 5: user
	
	animation 6: target, mirror

等待x帧。通过用几帧代替一帧来延长时间。为了更方便，你可以用x帧来等待播放。

***
#### CAST ANIMATION
***

Plays an animation on the skill’s user. Will not occur if the action is an item or the user’s default normal attack.

Usage Example: 

	cast animation

在技能使用者身上播放动画。如果这个动作是默认动作，就不会发生。

***
#### CLEAR BATTLE LOG
***

Clears all the messages at the top of the screen.

Usage Example: 
	
	clear battle log

清除屏幕顶部信息。

***
#### DEATH BREAK
***

If a user were to die for any reason during the middle of the skill (either via counter attack or reflection), this will force the remainder of the action sequences for the part of the skill/item to shut down and be skipped.

Usage Example: 
	
	death break

如果一个使用者在一场战斗中死亡（通过反击等等也算），这将会强制结束战斗序列。

***
#### DISPLAY ACTION
***

Displays the action’s name at the top of the battle log. It will remain there until the battle log is cleared.

Usage Example: 

	display action

在战斗记录里显示动作名称。这将一直持续到记录被清理。

***
#### IF … ELSE STATEMENTS
***

For those familiar with programming, you can use if…else statements to perform different actions based on different conditions. Use ‘if’ to specify a block of code to be executed, if a specified condition is true. Use ‘else’ to specify a block of code to be executed, if the same condition is false. Use ‘else if’ to specify a new condition to test, if the first condition is false. Use ‘end’ to specify where the conditions are to end.

对于程序集合，你可以使用这个语句来在不同情况下使用不同行动。使用if语句来设定一个特殊情况。使用else语句来设定除此之外的情况。else if语句来设定除特定情况外的其他特定情况。使用end来结束。

Usage Example:
	
	if $gameSwitches.value(1)
	
	action effect

	else if $gameSwitches.value(2)

	action effect

	action effect

	else

	action effect

	action effect

	action effect

	end
*Note: You do not have to indent the code in between to work. It just looks better that way in your action sequences.

注意：你不必要按照标准格式来书写代码。但是标准格式会看起来很舒服。

***
#### IMMORTAL: targets, true/false
***

Sets the targets to a state of immortality so that they don’t die in the middle of an attack. This is to ensure every action effect goes through.

Usage Example: 

	immortal: targets true
	
设置永久状态使其不会再战斗中消失。这将确保所有行动效果都发生。

***
#### MOTION WAIT: target
***

Makes the game wait 12 frames if the target(s) performing the action is an actor. If the target(s) is not an actor, no waiting will be done.

Usage Example: 

	motion wait: user
	
如果对象是角色，则等待12帧。如果不是角色，则不需要等待。

***
#### PERFORM ACTION
***

Causes actors to step forward and swing their weapon, thrust it, however the motion that is determined will be automatically done by the game.

Usage Example: 

	perform action

使角色上前行走一步并挥舞武器，或者推击。这个在系统默认中是自动执行的。
***
#### PERFORM FINISH
***

Causes actor to move back to its home spot.

Usage Example: 

	perform finish

使角色向后回到初始位置。	

***
#### PERFORM START
***

Causes actor to move forward from its home spot.

Usage Example: 

	perform start	

是角色向前回到初始位置。

***
#### WAIT: frames
***

Makes the game wait a certain amount of frames before going on to the next action in the action sequence.

Usage Example: 
	
	wait: 60
	
在进行行动序列的下一步之前等待确定的帧数。

***
#### WAIT FOR ANIMATION
***

Waits for all animations to finish before going on to the next action in the action sequence.

Usage Example: 

	wait for animation
	
在进行行动序列的下一步之前等待所有动画播放完毕。

***
#### WAIT FOR EFFECT
***

Waits for all effects to finish playing before continuing on.

Usage Example: 

	wait for effect

在继续之前等待所有效果发生完毕。

***
#### WAIT FOR MOVEMENT
***

Waits for all battler movements to finish before going on to the next action in the action sequence.

Usage Example: 

	wait for movement
	
在进行行动序列的下一步之前等待所有战斗移动完成。

***
#### WAIT FOR NEW LINE
***

Waits for a new line to appear in the log window before going on to the next action in the action sequence.

Usage Example: 

	wait for new line

在进行行动序列的下一步之前等待一条记录窗口的新的线。

***

### Happy RPG Making!

