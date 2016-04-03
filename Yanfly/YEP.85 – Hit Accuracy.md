##YEP.85 – Hit Accuracy
***
###Introduction
***
By default, RPG Maker MV’s action accuracy formula is unintuitive. For what it matters, the accuracy of the skill is determined first, then the evasion of the target is determined second regardless of the accuracy of the first check. This means that even if an attacker has 1000% HIT accuracy, the skill can still be evaded by the enemy’s 5% EVA stat. So instead, this plugin will provide control over an action’s accuracy formula and evasion formula. By this plugin’s default settings, accuracy will now be calculated where the attacker’s HIT and the enemy’s EVA are set against one another for a more intuitive accuracy formula.

默认来说，MC的行动公式是繁杂的，我们将先验证技能精准性，在验证目标躲避率。这意味着即使玩家拥有1000%的伤害精准，技能仍然有可能被5%的躲避率躲避。这个插件提供了行动精准公式的调整。在插件默认设置里面，精准性将会被更简便的公式计算

***
###Instructions
***

This plugin can be plug-and-play. But, if you wish to modify the accuracy formulas to your liking, adjust the plugin parameters that alter each of the individual aspects.

这个插件是即插即用。但是，如果你想调整你想要的公式，可以调整插件参数

skillHitRate – This is the inherent success rate of the skill/item.

技能成功率

userHitRate – This is the accuracy rate of the user. If it’s a physical action, by default, HIT is used. If it’s a magical action, by default, there will be a 100% modifier from it, meaning it doesn’t alter the success rate.

行动成功率

targetEvadeRate – This is the evasion rate of the target. If it’s a physical action, the EVA stat is used by default. If it’s a magical action, the MEV stat is used by default.

目标躲避率

***
###Happy RPG Making!

