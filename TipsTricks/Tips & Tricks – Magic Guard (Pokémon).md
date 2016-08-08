## Tips & Tricks – Magic Guard (Pokémon) – RPG Maker MV
Magic Guard is a passive ability from Pokémon that prevents indirect damage dealt from states such as Poison. With this Tips & Tricks, you can recreate the effect in MV, too!
魔法防御是一个来自神奇宝贝游戏的被动能力，他可以阻止类似中毒导致的间接伤害，通过这期教程，你可以在MV中制作这样的能力

**必备插件：**
1. Auto Passive States
2. Buffs States Core
3. Extra Parameter Formula
**步骤：**
1. 设置魔法防御状态Magic Guard ，在备注Note里面，写上\<HRG Rate:0%\>来抵消持续伤害
2. 设置被动状态插件，将魔法防御状态Magic Guard 设置为被动持有
3. 如果是系统
2. 设置中毒状态Toxic，在备注Note里面复制粘贴上述代码
	<Custom Apply Effect>
	this.\_toxicCounter = 1;
	</Custom Apply Effect>
	<Custom Regenerate Effect>	 
	// This will check if the Magic Guard state exists.
	if (!user.isStateAffected(178)) {
	 var n = this.\_toxicCounter / 16;
	var value = Math.floor(n \* user.mhp \* -1);
	user.gainHp(value);
	this.\_toxicCounter += 1;
	} // End check for Magic Guard 
	</Custom Regenerate Effect>