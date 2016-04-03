##YEP.84 – Area of Effect
***
###Introduction
***

This plugin requires YEP_BattleEngineCore and YEP_TargetCore. Make sure this plugin is located under YEP_BattleEngineCore and YEP_TargetCore in the plugin list.

这个插件需要YEP_BattleEngineCore和YEP_TargetCore，请放置于它们下面

Sometimes, targeting one foe isn’t enough and targeting all foes is too many. The right mix in between would be area of effects to target only a certain area of foes. This plugins enables area of effect targeting to come in the forms of circular areas, column areas, row areas, and even the whole screen.

有时，命中一个目标太大，命中全部又太多。最好能够命中指定区域的人。这个插件可以设置圆形区域，横排，竖排等

***
###Instructions – Understanding Area of Effect
***

Area of effect scopes don’t necessarily select just one target but instead, a group of targets that are close together. Any targets outside of range from the area of effect zone will be added to the scope of targets for the skill or item being used.

范围攻击不需要指定某个目标，而是指定范围。

Whether or not the targets will be struck is relative to the target’s hitbox settings. Normally, this is dependent on the target’s graphic, but you can set individual hitbox settings for the target using notetags as well.

这个范围取决于敌方图像，当然你也可以额外单独设置它们

***
###Notetags
***

You can use the following notetags to apply area of effect scopes for your skills and items!

你可以使用下面标签

###Skill and Item Notetags:

— AOE Circle Scope —

	<AOE Radius: x>
Turns the skill into having a target scope with a circular AOE. x is the amount of pixels of the radius for the AOE Circle.

圆形半径

	<AOE Height Rate: x%>
Changes the height to be x% of the diameter of the AOE Circle.

圆形半径高度改变率

	<AOE Graphic: filename>
If you wish to use a different image for the AOE circle for this skill or item, replace ‘filename’ with the filename of the graphic found within the img/pictures/ folder. Do not include the file extension. For example, the graphic ‘aoeblue.png’ will result in notetag <AOE Graphic: aoeblue>.

范围攻击使用的图片

	<AOE Hue: x>
This will change the hue of the AOE circle to x. By default, the hue value is 0. This will alter the color of it.

范围色调

	<AOE Blend: x>
This is the blend mode used for the AOE graphic. 0 is normal with no blend modes applied. 1 is additive. 2 is multiply. 3 is screen.

混合模式

— AOE Rectangle Scope —

	<Rect Column: x>
This will make a rectangular area of effect scope that is x pixels wide. The area of effect zone is vertical and all targets within this zone will become targets for the action.

矩形竖排

	<Rect Row: x>
This will make a rectangular area of effect scope that is x pixels tall. The area of effect zone is horizontal and all targets within this zone will become targets for the action.

矩形横排

	<Rect Screen>
This will target all units within the entirity of the screen. While it is the same as an all enemies/all allies scope, this can be used to give a visual representation of which units are selected as a target.

矩形全屏

<Rect Graphic: filename>
If you wish to use a different image for the AOE rectangle for this skill or item, replace ‘filename’ with the filename of the graphic found within the img/pictures/ folder. Do not include the file extension. For example, the graphic ‘rectblue.png’ will result in notetag <AOE Graphic: rectblue>.

矩形图片

	<Rect Hue: x>
This will change the hue of the AOE rectangle to x. By default, the hue value is 0. This will alter the color of it.

矩形色调

	<Rect Blend: x>
This is the blend mode used for the AOE graphic. 0 is normal with no blend modes applied. 1 is additive. 2 is multiply. 3 is screen.

矩形混合模式

— Animation Settings —

	<AOE Center Animation>
This will cause the animation for an AOE skill to be played to center on the first target of the AOE group, which is usually the center of the AOE targets.

范围攻击中心动画

	<AOE Group Animation>
This will cause the animation for an AOE skill to be played on all of the targets within the AOE group as if normally done.

范围群组动画

####Actor and Enemy Notetags:

— AOE Hitbox Settings —

	<AOE Buffer X: +x>
	<AOE Buffer X: -x>

	<AOE Buffer Y: +x>
	<AOE Buffer Y: -x>
Changes the buffer x/y of the battler when an AOE image is placed on the battler. This is also the offset from the center location at which the AOE targets will be calculated, too. If this notetag isn’t used, the buffer value used will be from the plugin parameters.

改变缓存区范围

	<AOE Hitbox Width: x>
	<AOE Hitbox Height: x>
This will adjust the hitbox of the battler to have an AOE hitbox width of x or an AOE hitbox height of x.

改变命中区范围

***
###Graphics
***

For those in need of AOE Circle and AOE Rectangle graphics, save these into your img/pictures/ folder from within your project folder~

对于需要图片的人，可以使用下面的图片

***
###Happy RPG Making!