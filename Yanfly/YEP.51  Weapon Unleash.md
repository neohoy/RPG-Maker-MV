##  YEP.51 – Weapon Unleash

***
###Introduction
***

This plugin allows your game to be able to replace the Attack and Guard commands or give them the option of having a skill randomly occur when using them in reference to Golden Sun’s Weapon Unleash system!

这个插件可以让你的游戏代替攻击和防御命令，或者放入技能的选项。这个插件参考了Golden Sun的插件

When replacing the Attack and Guard commands, the text can be changed out for the command names as well. These replacements aren’t limited to just equipment in origin, but also from actors, classes, enemies, equipment, and states, too!

当替代攻击和防御命令，可以改变命令的名字。这些替换不仅仅在装备，也可以是角色，职业，敌人，状态等等

***
###Notetags
***

There’s a few notetags you can use to replace the default attack and provide any weapon unleash effects. Note: If you’re using notetags that write out the skill’s name and you have multiple skills in your database with the same name, priority will be given to the skill with the highest ID.

这里有一些标签，你可以使用它们来替代默认的攻击命令，提供武器发动效果。注意：如果你使用了标签写了技能名字，并且你有多个重复名字的技能，那么将会优先自行ID最高的技能。

####Actor, Class, Enemy, Weapon, Armor, State notetags:

— Replace Attack —

	<Replace Attack: x>
	<Replace Attack: name>
This will replace the attack skill used by the battler. If a battler would have multiple attack replacements, priority will be given in the following order in a first-come-first-serve aspect:

这个将会替代攻击技能。如果你的攻击命令有多个替代，会按照下面的顺序，先进先生效

>States – Highest to Lowest Priority  
Equipment – In order of equip list  
Enemy Aspect  
Class Aspect  
Actor Aspect  

>状态 从高到低  
>装备 装备列表顺序  
>敌人  
>职业  
>角色  

— Replace Guard —

	<Replace Guard: x>
	<Replace Guard: name>
This will replace the guard skill used by the battler. If a battler would have multiple guard replacements, priority will be given in the following order in a first-come-first-serve aspect:

这个将会替代防御技能。如果你的防御命令有多个替代，会按照下面的顺序，先进先生效

>States – Highest to Lowest Priority  
Equipment – In order of equip list  
Enemy Aspect  
Class Aspect  
Actor Aspect  

>状态 从高到低  
>装备 装备列表顺序  
>敌人  
>职业  
>角色  

— Weapon Unleash —

	<Weapon Unleash x%: y>
	<Weapon Unleash x%: name>
This causes the Attack skill to have a x% chance to randomly use skill y (or named). This will apply only to the Attack Command. Insert multiple copies of this notetag to give more weapon unleashes. If a battler would have multiple weapon unleashes, the randomization check will occur in the following order:

这会造成攻击技能有x%的概率使用技能y。这仅仅在攻击命令生效。你可以插入多个副本来生成更多的武器发动技能。如果一个战斗者有多个武器发动技能，会按照下面顺序随机计算

>States – Highest to Lowest Priority  
Equipment – In order of equip list  
Enemy Aspect  
Class Aspect  
Actor Aspect  

>状态 从高到低  
>装备 装备列表顺序  
>敌人  
>职业  
>角色  

If a weapon unleash check passes earlier in the list while there are still weapon unleashes later in the list, that weapon unleash will take priority and override all the following weapon unleashes.

如果武器发动效果在列表中较早通过，并且后续列表还有武器发动效果，那么后续发动效果会被优先重写。

— Guard Unleash —

	<Guard Unleash x%: y>
	<Guard Unleash x%: name>
This causes the Guard skill to have a x% chance to randomly use skill y (or named). This will apply only to the Guard Command. Insert multiple copies of this notetag to give more guard unleashes. If a battler would have multiple guard unleashes, the randomization check will occur in the following order:

这会造成防御技能有x%的概率使用技能y。这仅仅在防御命令生效。你可以插入多个副本来生成更多的武器发动技能。如果一个战斗者有多个武器发动技能，会按照下面顺序随机计算

>States – Highest to Lowest Priority  
Equipment – In order of equip list  
Enemy Aspect  
Class Aspect  
Actor Aspect  

>状态 从高到低  
>装备 装备列表顺序  
>敌人  
>职业  
>角色  

If a guard unleash check passes earlier in the list while there are still guard unleashes later in the list, that guard unleash will take priority and override all the following guard unleashes.


如果防御发动效果在列表中较早通过，并且后续列表还有防御发动效果，那么后续发动效果会被优先重写。

— Unleash Rate Modifiers —

	<Weapon Unleash: +x%>
	<Weapon Unleash: -x%>
This alters the weapon unleash rate for all weapon unleashes by +x%/-x%.

对于所有武器发动效果概率增加或者减少x%

	<Weapon Unleash x: +y%>
	<Weapon Unleash x: -y%>
	<Weapon Unleash name: +y%>
	<Weapon Unleash name: -y%>
This alters the weapon unleash rate for skill x (or name) by +y%/-y%. If you are using the named notetag and you have multiple skills in your database that use multiple names, priority will be given to the skill with the highest ID.

改变武器发动效果为技能x的概率增加或者减少y%。如果你使用了名字标签并且拥有多个重复的名字，优先执行ID最高的

	<Guard Unleash: +x%>
	<Guard Unleash: -x%>
This alters the weapon unleash rate for all weapon unleashes by +x%/-x%.

对于所有防御发动效果概率增加或者减少x%

	<Guard Unleash x: +y%>
	<Guard Unleash x: -y%>
	<Guard Unleash name: +y%>
	<Guard Unleash name: -y%>
This alters the guard unleash rate for skill x (or name) by +y%/-y%. If you are using the named notetag and you have multiple skills in your database that use multiple names, priority will be given to the skill with the highest ID.

改变防御发动效果为技能x的概率增加或者减少y%。如果你使用了名字标签并且拥有多个重复的名字，优先执行ID最高的

####Skill Notetags:

	<Command Text: x>
	<Attack Text: x>
	<Guard Text: x>
If you are using Replace Attack or Replace Guard, you can change the way the command name appears in the actor command window to x. If you are using the <Command Text: x> notetag, this will apply to both Attack and Guard names.

如果你替代了攻击或者防御命令，你可以改变显示的命令名字。如果你使用<Command Text: x>的标签，这将应用于攻击和防御。

***
### Happy RPG Making!