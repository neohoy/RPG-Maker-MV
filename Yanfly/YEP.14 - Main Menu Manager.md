## YEP.14 – Main Menu Manager
Have more control over your main menu straight from the Plugin Manager. Add, remove, hide, show, enable, disable commands from your main menu altogether!

这可以让你对游戏主菜单直接控制，集合了添加，移除，隐藏，显示，开启，关闭等命令

***
- ### Introduction
***

For those who wish to alter the various aspects of the main menu commands without needing to touch the source code can use this plugin to do so. Although this plugin mostly ports the menu creation process to the Plugin Manager parameters, it allows for a cleaner way to handle the menu command management process.

对于希望改变主菜单各个方面内容的人来说，不需要接触源代码，使用这个插件就可以做到。尽管这个插件在插件参数里面设置了很多菜单生成的方案，但它依然考虑了采用一个简洁的方式来处理菜单命令。

***
- ### How to Use This Plugin
***

Each section in the parameters is divided up into various parts. Each of these parts play a role in how the menu command functions. Here’s what each part does:

参数里被分成不同的部分。每个部分都发挥了菜单的不同功能。下面是每个部分的定义。

**Name**
– This is how the command will appear visually in the main menu. This is an eval, which means, it’s code driven. If you want the command to appear just as it is, use ‘quotes’ around it.

名字-这是在主菜单实际显示的内容。这是一个函数，这意味着，是代码驱动的。所以如果你想要菜单就是显示你输入的文本，请使用引号('')

**Symbol**
– This is the identifier for the command. Each command should have a unique symbol, so much as to not cause conflicts with each command. However, shared symbols are perfectly fine as long as you’re fine with them performing the same function when selected.

符号-这是命令的ID。每个命令应该有独有的符号，这样不同命令之间就不会发生冲突。只要你明白被选择的菜单发挥相同的功能，共享符号也是可以的。

**Show**
– This is an eval condition for whether or not the command shows up in the main menu. If you wish for this to always show up, simply use ‘true’ without the quotes.

显示-这是一个关于菜单是否显示的函数状态。如果你希望它显示出来，可以使用没有引号的true

**Enabled**
– This is an eval condition for whether or not the command is enabled. The difference between showing a command and enabling a command is that a command can show, but it can’t be selected because it isn’t enabled. If you wish for this command to always be enabled, use ‘true’ without the quotes.

开启-这是一个关于菜单是否开启的函数状态。这和显示命令不同的地方在于，如果菜单不是开启状态，那么即便显示出来也无法选择。如果你希望它开启，可以使用没有引号的true

**Ext**
– Stands for extension. This serves as a secondary symbol for the command and it can be used for pretty much anything. It has no direct impact on the command unless the command’s objective is related to the extension value. The majority of commands do not need to make use of the Ext value.

拓展-这代表拓展功能。这个服务是作为辅助符号使用的，他可以用来做很多事情。除非你想要命令和某个拓展值联系起来，否则他没有直接的影响。大多数命令不需要使用拓展值

**Main Bind**
– This is an eval function that is to be ran when this command is selected straight from the main menu. The function that is to be bound to this command needs to be accessible from Scene_Menu is some way or another. For commands that are meant to select an actor first, use ‘this.commandItem.bind(this)’ without the quotes.

主要绑定-这是函数式，当菜单被选择时，它就会运行。这个功能主要是用来绑定命令，这就允许你可以用各种方式来打开视图。对于命令来说，你可以先选择一个角色，然后用this.commandItem.bind(this)这段命令。

**Actor Bind**
– This is an eval function that is to be ran when an actor is selected after choosing this command, usually to push a scene. This function isn’t needed for any menu commands that don’t require selecting an actor.

角色绑定-这是函数式。当你选择一名角色再来选择菜单时，他就会运行，通常用来展示。当不需要特定角色展示时，这个功能可以不使用。

***
- ###Examples
***

The following are some examples to help you add/alter/change the way commands appear for your main menu.

下面是一些例子来帮助你通过命令来制作主菜单

	Name: TextManager.item
	Symbol: item
	Show: this.needsCommand(‘item’)
	Enabled: this.areMainCommandsEnabled()
	Ext:
	Main Bind: this.commandItem.bind(this)
	Actor Bind:

The item command is made using the above example. ‘TextManager.item’ is how the command name will appear. It draws the name information from the database Text Manager entry for ‘Item’ and uses whatever you put into the database in here. The symbol ‘item’ is used to make the item command’s unique identifier. In order for the command to show, it will run a ‘needsCommand’ function to check if it will appear. This ‘needsCommand’ function is related to your database on whether or not you want the item to appear there. In order for this command to be enabled, it will check for whether or not the main commands are enabled, which is related to whether or not there are actors in the current party. And finally, the line of code ‘this.commandItem.bind(this)’ is the command that will run once the item entry is selected.

物品菜单就是用这命令制作的。TextManager.item就是绑定名字，这个名字来源于数据库的Item选项。符号item就是用来做这个菜单的特殊ID。为了让菜单显示出来，这里用needsCommand函数来检查，这个函数将和数据库设置的item选项关联，来决定是否显示。为确保菜单开启，我们将会检查主菜单是否开启，这和初始队伍里有无角色有关。最后，this.commandItem.bind(this)是用来开启物品菜单的。

	Name: TextManager.skill
	Symbol: skill
	Show: this.needsCommand(‘skill’)
	Enabled: this.areMainCommandsEnabled()
	Ext:
	Main Bind: this.commandPersonal.bind(this)
	Actor Bind: SceneManager.push(Scene_Skill)

The skill command is made using the above example. ‘TextManager.skill’ is how the command name will appear. It draws the name information from the database Text Manager entry for ‘Skill’ and uses whatever you put into the database in here. The symbol ‘skill’ is used to make the skill command’s unique identifier. In order for the command to show, it will run a line code ‘needsCommand’ function to check if it will appear. This ‘needsCommand’ function is related to your database on whether or not you want the skill option to appear there. In order for this command to be enabled, it will check for whether or not the main commands are enabled, which is related to whether or not there are actors in the current party. This time, the main bind command is to send the player to the actor selection process using ‘this.commandPersonal.bind(this)’ instead. Once the player selects an actor, ‘SceneManager.push(Scene_Skill)’ is then ran to send the player to Scene_Skill to manage the actor’s skills.

技能菜单就是用这命令制作的。TextManager.skill就是绑定名字，这个名字来源于数据库的skill选项。符号skill就是用来做这个菜单的特殊ID。为了让菜单显示出来，这里用needsCommand函数来检查，这个函数将和数据库设置的item选项关联，来决定是否显示。为确保菜单开启，我们将会检查主菜单是否开启，这和初始队伍里有无角色有关。这次，我们的主要绑定命令会用this.commandPersonal.bind(this)来替代。一旦玩家选择了一名角色，SceneManager.push(Scene_Skill)将会运行来打开角色技能管理。

	Name: ‘Common Event 1’
	Symbol: common event
	Show: false
	Enabled: true
	Ext: 1
	Main Bind: this.callCommonEvent.bind(this)
	Actor Bind:

This is a customized command that is included by default with the plugin. This command’s name is ‘Common Event 1’, but it can be changed to whatever you want by simply changing what’s in between the ‘quotes’ in the parameter settings. The symbol is the identifier for all common events. However, by default, this common event item does not show in the main menu. If you want it to appear, set the Show option to ‘true’ without the quotes and it will appear. Because the Enabled option is ‘true’, the command can always be selected by the player. The Ext actually has a role with this command. The Ext determines which common event is to be played. In this example, the Ext value is 1, which means common event 1 will be ran when this command is selected. Should the Ext value equal to 25, it will be common event 25 that will run once this command is selected. The reason is because the Main Bind for this command option is ‘this.callCommonEvent.bind(this)’, which is a function included in this plugin to allow for common events to be ran.

这是一个插件默认包含的定制菜单命令。命令名字为公共事件1，但是你可以通过参数设置引号内的文本来自定义。这个符号就是对于所有的公共事件。然而，默认的公共事件选项是隐藏的，因此如果你需要，可以设置显示选项为true。这个命令默认是开启可以被选择的。拓展值实际上发挥了很大的作业，它意味着哪个公共事件被执行。在这里例子，拓展值是1，所以公共事件1将会在菜单被选中时执行，如果设置为25，则公共事件25会被执行。其原理是主要绑定的命令为this.callCommonEvent.bind(this)。这是一个允许公共事件执行的函数。

***

## Happy RPG Making!

