## YEP.16 – Battle A.I. Core
Tired of dumb enemies that turn your otherwise challenging game into an easy-peasy walk in the park? The Battle A.I. Core plugin allows you to manually adjust the settings and patterns of your enemies so that they can deliver MANLY poundings onto your players.

是否厌倦了简单傻瓜的敌方让你的游戏没有挑战性，就像在公园里散步一样简单？智能战斗系统插件可以让你调整敌方的设置和样式，这样他们就可以更加类似人类操作一般对付你的角色。

***
### Introduction
***

RPG Maker MV’s default enemy AI is a bit lackluster even if you managed to have it based completely on the rates and switches. There is no way to control the way the enemy chooses targets by default, nor are the conditions imposed by the default editor enough to satisfy the majority of checks. This plugin enables you to set a priority list of conditions, actions, and the targets selected for the enemy to go through before making a decision on how to participate in battle.

RPG Maker MV的

These conditions contain all of the default editor’s conditions plus more, such as determining the parameter values of a target, whether or not a state exists on a target, the target’s elemental weakness (or resistances), and more before deciding an action. Furthermore, you can set an AI level for the enemies to make them more consistent in the way they go about fighting your players or more random in the way the enemies treat the priority list, too.

Parameters

Dynamic Actions
By default, the enemy’s actions are determined at the start of the turn. While this works in its own right, enabling Dynamic Actions allow enemies to make a decision when the enemy’s turn comes up instead. This prompts enemies to be more flexible and to appear more intelligent in battle, thus, giving your players a bit more of a challenge.

Element Testing
If this is disabled, enemies will automatically know the elemental weakness, resistance, etc. about all actors. If enabled, enemies will need to test out the skills on various actors first before making a decision. Until the enemy learns about the actor’s elemental rates, the enemy is always willing to try using the skill on the target actor. However, if the skill itself does not possess an element, then no information will be registered. All elemental data is reset at the start of each battle for all enemy parties.

Default AI Level
Not all enemies are intelligent. In fact, some of them are dumb or random. Setting the AI Level of a foe at a low number means the foe is more random while a higher AI Level foe is more consistent. How the AI Level works is, a random number will be checked from 0 to 99. If that enemy’s AI Level is higher than that number, that action is checked to see if the condition is fulfilled or not. If the AI Level is lower than that number, the condition is automatically deemed false and continues on to the next action. The check is ran each time a new action is checked upon. This random factor is only applied to <AI Priority> lists and do not apply to default actions.

Enemy AI Level

Enemy AI levels do not determine how difficult they are. Instead, they determine how strictly they will follow the <AI Priority> lists. An AI Level of 80 means it has an 80% chance of following the prioritized action on the AI Priority list before moving onto the next one where there will be another 80% chance and so on. If the AI level is lower, the chance is lower, making the AI to be more random.

Enemy Notetag:
<AI Level: x>
Sets the enemy’s AI level to x. The lower x, the more random the enemy. The higher for x, the more strict the enemy is about following the AI Priority list found in its notebox, too.

Enemy AI Priority

If an enemy has an AI Priority list, the enemy will go down that list from top to bottom (giving the actions at the top more priority than the ones at the bottom) looking for any actions whose conditions are fulfilled. If that condition is fulfilled, then that action will be the action the enemy will partake in.

To set up a Priority List for the enemy, you must place inside the enemy’s notebox notetags that match the following format:

<AI Priority>
condition: SKILL x, target
condition: SKILL x, target
</AI Priority>

or

<AI Priority>
condition: skill name, target
condition: skill name, target
</AI Priority>

Any number of conditions and skills can be placed in between the two <AI Priority> tags. You can choose to use skill ID’s or the skill names. However, if you use the skill names, keep in mind that it is not case sensitive and if any skills in your database have matching names, the skill with the larger skill ID will be the action used.

Conditions

The following is a list of ways you can format your conditions for the enemy to choose the right skill. In addition to deciding whether or not the skill will be used, the condition also selects the enemy target. The following list will tell you how the conditions are met and what targets will be selected for battle.

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
ALWAYS
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This condition will always be fulfilled. The valid target group is all targets within scope.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Always: Skill 10, Lowest HP%
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
ELEMENT X case
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This allows you to match the element rate of element X (use either a number or the name of the element in place of ‘X’) to see whether or not the conditions for the action are fulfilled. Replace ‘case’ with ‘Neutral’ for normal element rate, ‘Weakness’ for anything above 100% element rate, ‘Resistant’ for below 100% element rate, ‘Null’ for 0% element rate, and ‘Absorb’ for below 0% element rate. Valid targets will be those with the matching element rates.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Element Fire Weakness: Fireball, Lowest HP%
Element Water Resistant: Water Cancel, Highest MAT
Element 4 Null: Earthquake, Lowest MDF
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
 EVAL eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This allows you to use any kind of code to check and fulfill a condition. This condition uses all alive members of the skill’s scope as valid targets.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Eval user.name() === ‘Bat A’: Skill 10, Highest HP%
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
group ALIVE MEMBERS eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Replace ‘group’ with either ‘party’ for the player’s party or ‘troop’ for the enemy party. This runs the number of party alive members or troop alive members in a check to see if the conditions can be fulfilled.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Party Alive Members > 2: Skill 10, Lowest HP%
Troop Alive Members <= 4: Skill 11, Highest HP%
Troop Alive Members === $gameVariables.value(3): Skill 12, Random
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
group DEAD MEMBERS eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Replace ‘group’ with either ‘party’ for the player’s party or ‘troop’ for the enemy party. This runs the number of party dead members or troop dead members in a check to see if the conditions can be fulfilled.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Party Dead Members > 2: Undead, Highest ATK
Troop Dead Members <= 4: Life, Highest ATK
Troop Dead Members === $gameVariables.value(3): Skill 12, Random
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
stat PARAM eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Replace ‘stat’ with either ‘atk’, ‘def’, ‘mat’, ‘mdf’, ‘agi’, ‘luk’, ‘maxhp’, ‘maxmp’, ‘hp’, ‘mp’, ‘hp%’, ‘mp%’, or ‘level’ to run it in a condition check again to see if the action gets passed. The group that it checks will be based on the skill’s scope. If the skill targets foes, then all foes will take a check to see if they fulfill the conditions. Likewise for party members if the skill is for allies. The valid targets will be those who pass the condition check.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: HP% param <= 50%: Heal, Lowest HP%
MP param > 90: Mana Drain, Highest MP
ATK param > user.atk: Power Break, Highest ATK
LEVEL param > 10 && target.notState(5): Blind, Random
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
type PARTY LEVEL eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Replace ‘type’ with either ‘highest’, ‘lowest’, or ‘average’ to get the respective party level for the skill’s scope. This will reference the entire party’s level. If this condition is fulfilled, all targets would will become valid targets.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Highest Party Level > 10: Skill 10, Lowest MP%
Lowest Party Level < 12: Skill 11, Lowest HP%
Average Party Level > 15: Skill 12, Highest HP%
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
RANDOM x%
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This will make the condition based on a random x percent chance. This condition allows all possible targets to be valid for targeting.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Random 50%: Skill 10, Lowest HP%
Random 75%: Skill 11, Highest HP%
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
STATE === state x
STATE === state name
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This will detect if the target scope has state x (or state name if you use that instead). If the target does, that target is added into the pool of valid targets. Any targets not affected by the state will be ignored.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: State === State 5: DeBlind, Highest ATK
State === Knockout: Life, Random
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
STATE !== state x
STATE !== state name
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This will detect if the target scope does not have state x (or state name if you use that instead). If the target doesn’t, that target is added into the pool of valid targets. Any targets affected by the state will be ignored.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: State !== State 12: Haste, Random
State !== Courage: Cowardice, Highest ATK
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
SWITCH X case
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Replace ‘x’ with the ID of the switch you wish to check. Replace ‘case’ with either ‘on’ or ‘off’ (you may also use ‘true’ or ‘false’). If the switch matches the case, the condition is fulfilled and all skill targets become valid targets.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Switch 5 On: Skill 10, Lowest HP%
Switch 6 Off: Skill 11, Highest HP%
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
TURN eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This will make the condition based on the turn count to be fulfilled by an eval statement. This condition allows all possible targets to be valid for targeting.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Turn > 3: Skill 10, Lowest hp%
Turn === 4: Skill 11, Highest hp%
Turn <= $gameVariables.value(2): Skill 12, Random
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-
VARIABLE X eval
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
This will call forth the value of variable ‘x’ to partake in an eval comparison to see if the condition is fulfilled. If it is, all skill targets become valid targets.
– – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – – –
Example: Variable 3 > 10: Skill 10, Lowest HP%
Variable 5 <= 100: Skill 11, Highest HP%
Variable 2 === user.atk: Skill 12
=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-

Targeting

Targeting is optional but can be done via a small change to the condition. All you have to do is add a ‘,’ after the skill to indicate which target in the valid target group you would like to target. For example:

Random 50%: Fire, Highest HP%

The condition to be met is the 50% random chance, but if it is fulfilled, the target selected will be the member on the targeting scope’s team with the highest HP percentage. When that happens, the ‘Fire’ skill will be used upon that target.

If no target is specified, a random target will be selected amongst the group of valid targets. Otherwise, refer to the following list:

—————————————————————————-

<<nothing>>
Selects a random member of the valid target group.

First
Selects first member of the valid target group.

Highest MaxHP
Selects highest MaxHP valid target.

Highest HP
Selects highest HP valid target.

Highest HP%
Selects highest HP% valid target. *Note1

Highest MaxMP
Selects highest MaxMP valid target.

Highest MP
Selects highest MP valid target.

Highest MP%
Selects highest MP% valid target. *Note1

Highest ATK
Selects highest ATK valid target.

Highest DEF
Selects highest DEF valid target.

Highest MAT
Selects highest MAT valid target.

Highest MDF
Selects highest MDF valid target.

Highest AGI
Selects highest AGI valid target.

Highest LUK
Selects highest LUK valid target.

Highest Level
Selects highest Level valid target. *Note2

Lowest MaxHP
Selects lowest MaxHP valid target.

Lowest HP
Selects lowest HP valid target.

Lowest HP%
Selects lowest HP% valid target. *Note1

Lowest MaxMP
Selects lowest MaxMP valid target.

Lowest MP
Selects lowest MP valid target.

Lowest MP%
Selects lowest MP% valid target. *Note1

Lowest ATK
Selects lowest ATK valid target.

Lowest DEF
Selects lowest DEF valid target.

Lowest MAT
Selects lowest MAT valid target.

Lowest MDF
Selects lowest MDF valid target.

Lowest AGI
Selects lowest AGI valid target.

Lowest LUK
Selects lowest LUK valid target.

Lowest Level
Selects lowest Level valid target. *Note2

Note1: This is calculated by dividing the current HP with the MaxHP or the current MP with the MaxMP.

Note2: If this is used on an enemy without a proper enemy level plugin installed, this will return the player party’s highest level.

Happy RPG Making!

