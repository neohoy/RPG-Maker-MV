## YEP.34  Subclass
Requires the Class Change Core plugin. This plugin enables your actors to be able to have a secondary class as a subclass! Subclasses can carry over skills, skill types, traits, and stats! How they carry it over is entirely up to you!

这个插件需要Class Change Core的插件。这个插件可以让你的游戏角色拥有第二个职业作为副职业！副职业可以涵盖所有技能，技能类型，特性和状态等等！它们涵盖的方式将由你来决定！

***
- ### Introduction
***

This plugin requires YEP_ClassChangeCore. Make sure this plugin is located under YEP_ClassChangeCore in the plugin list.

这个插件需要YEP_ClassChangeCore。请确保这个插件安装在YEP_ClassChangeCore的下面。

This class enables subclassing for your actors. Actors, when subclassing, can gain the benefits of the subclass, usually either by having access to the subclass skill set, weapons, and armor options. Also with this plugin, you can enable what kind of stat bonuses you can get by having a particular subclass enabled for the actor.

这个插件可以为你的角色开启副职业。当游戏角色获得副职业的时候，就可以获得相应的收益，可以开启例如副职业技能，武器，装备等等的选项。通过这个插件，你还可以为游戏角色获得额外的状态福利。

***
- ### Notetags
***

You can use the following notetags to modify subclassing aspects.

你可以使用下面的标签来改变副职业属性。

#### Actor Notetag:

	<Subclass: x>
	
> Sets the actor’s default subclass to x.

> 设置游戏角色默认的副职业为x

	<Restrict Class: x>
	<Restrict Class: x, x, x>
	<Restrict Class: x to y>

> This particular actor cannot switch his or her primary class to class(es) x (to y). This does not apply to the subclass. The actor can still change to this class via event.

> 特殊的角色不能切换他们的主职业类型。这个不会应用到副职业。但是游戏角色依然可以通过事件来改变职业

	<Restrict Subclass: x>
	<Restrict Subclass: x, x, x>
	<Restrict Subclass: x to y>

> This particular actor cannot switch his or her subclass to class(es) x (to y). This does not apply to the primary class. The actor can still change to this subclass via event.

> 特殊的角色不能切换他们的副职业类型。这个不会应用到主职业。但是游戏角色依然可以通过事件来改变职业

#### Class Notetags:

	<Primary Only>
	
> This class can only be class changed to a primary class and nothing more.

> 这个职业只可以作为主职业。

	<Subclass Only>
	
> This class can only be class changed to a subclass and nothing more.

> 这个职业只可以作为副职业。

	<Subclass x Combo Name: text>
	
> If this class is the primary and the subclass is class ID x, then the class name displayed will be ‘text’. For example, if the class combination is Warrior/Wizard, the name can appear as Spellblade.

> 如果当前职业是主职业，并且副职业的ID是x,则主职业的名字将会显示为t所输入文本。例如如果职业组合是武士/魔法师，则可以显示为魔剑士。

	<Hero Combo Name: text>
	<Warrior Combo Name: text>
	
> If you choose to use the class’s name instead, you can write out the name of the class in place of Subclass x. If you have multiple classes with the same name, priority will be given to the class with the highest ID.

> 如果你想使用职业名字来替代ID，你可以在之前x的地方写下名字。如果有多个职业具有相同的名字，则优先赋予给ID值最高的职业。

#### Skill and Item Notetags:

	<Require Class: x>
	<Require Class: x, x, x>
	<Require Class: x to y>
	
> Replace x with the class’s ID. This skill/item can only be used by the listed class(es) x. This does not apply to enemies.

> 使用职业ID替代x。这个技能或者物品只可以被职业x使用。这个并不能应用于敌方。

	<Require Subclass: x>
	<Require Subclass: x, x, x>
	<Require Subclass: x to y>
	
> Replace x with the class’s ID. This skill/item can only be used by the listed subclass(es) x. This does not apply to enemies.

> 使用职业ID替代x。这个技能或者物品只可以被副职业x使用。这个并不能应用于敌方。

***
- ### Plugin Commands
***

You can use these following plugin commands to change subclassing throughout the game!

你可以使用下面的插件命令来改变副职业选项

#### Plugin Command:

	ShowSubclass
	
> Shows the Subclass command in the Class Change Menu.

> 在职业菜单显示副职业选项

	HideSubclass
	
> Hides the Subclass command in the Class Change Menu.

> 在职业菜单隐藏副职业选项

	EnableSubclass

> Enables the Subclass command in the Class Change Menu.

> 打开主职业菜单的副职业选项

	DisableSubclass

> Disables the Subclass command in the Class Change Menu.

> 关闭主职业菜单的副职业选项

	ChangeSubclass x y
	
> Changes actor x’s subclass to y. Replace y with 0 to remove a subclass.

> 改变游戏角色x的副职业为y。你可以用0替代y来移除一个副职业。

***

### Happy RPG Making!

