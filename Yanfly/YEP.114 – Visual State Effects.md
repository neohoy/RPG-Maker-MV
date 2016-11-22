##YEP.114 – Visual State Effects – RPG Maker MV
###Introduction

This plugin requires YEP_BattleEngineCore and YEP_BuffsStatesCore. Make sure this plugin is located under both plugins in the plugin list.

这个插件需要YEP_BattleEngineCore和YEP_BuffsStatesCore。确保这个插件在他们下面

If you are running YEP_X_AnimatedSVEnemies, place this plugin under YEP_X_AnimatedSVEnemies on the plugin list for extra compatibility.

如果你正在使用YEP_X_AnimatedSVEnemies，把这个插件放在YEP_X_AnimatedSVEnemies下面来提高兼容度

States are amongst one of the most important aspects of the battle system. Therefore, relaying proper information to the player is extremely important. RPG Maker MV does relay information to the player about the various states and effects, but it is far from perfect. This plugin allows you to add more detail and visual effects regarding states to relay proper data.

状态是战斗系统中很重要的因素。因此展示适当的信息给玩家是非常重要的。RPG Maker MV 确实对多种状态和影响效果做了信息展示，然而远远不够完美。这个插件允许你添加更多细节，和视觉效果。

###Notetags

You can use the following notetags to give different various visual effects for your states.

你可以使用下面的备注来制作不同的影响效果

####State Notetags:

<code>
<State Motion: Walk>
<State Motion: Wait>
<State Motion: Chant>
<State Motion: Guard>
<State Motion: Damage>
<State Motion: Evade>
<State Motion: Thrust>
<State Motion: Swing>
<State Motion: Missile>
<State Motion: Skill>
<State Motion: Spell>
<State Motion: Item>
<State Motion: Escape>
<State Motion: Victory>
<State Motion: Dying>
<State Motion: Abnormal>
<State Motion: Sleep>
<State Motion: Dead>
</code>
– This allows you to set a custom motion when the battler is affected by this state. If a battler has multiple states with custom motions, then priority will go to the state with the highest priority number (in the database) with this state motion notetag.

这个允许你设置钻状态施加时的自定义动作。如果战斗者有多个状态自定义动作，将会优先执行状态动作备注里最优先的

	<State Animation: x>
– If a battler is affected by a state with this notetag, then a repeating animation x will play on the battler while in battle. If a battler is affected by multiple states with this notetag, then priority will go to the state with the highest priority number (in the database) with this state animation notetag.

设置自定义动作X

###Happy RPG Making!

