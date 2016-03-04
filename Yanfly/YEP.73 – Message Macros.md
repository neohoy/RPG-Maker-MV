##YEP.73 – Message Macros
***
###Introduction
***

This plugin requires YEP_MessageCore.js to run. Place this plugin under YEP_MessageCore.js in the plugin list.

这个插件需要YEP_MessageCore.js，请放在YEP_MessageCore.js下面

Ever get tired of having to do \n<\c[6]\n[1]\c[0]>? With this plugin you can create a macro where you can type \m[1] and it will do just that. This is a utility plugin for RPG Maker MV developers. Using this plugin, you can now develop macros for the message system or anywhere that uses text codes in general. This plugin will allow you to define what macro ID’s will change into what text in-game!

大家都厌倦了使用复杂的文本代码，现在你可以创造宏命令，只需要简单的代码即可实现之前的功能。

***
###Instructions – Setting Up Your macros
***

In the plugin parameters, you’ll see something along the lines of

在插件参数里，你可以看到这些

—Macro 1—

	Macro 1 Text \n<\c[6]\n[1]\c[0]>
	Macro 1 Name Harold

How this works is, whenever you type out ‘\m[1]’ in the Show Text event, it will convert that to ‘\n<\c[6]\n[1]\c[0]>’, which is then converted to its own text codes. The text written out is assigned by Macro 1 Text’s plugin parameter settings.

当你需要\n<\c[6]\n[1]\c[0]>时，你可以使用\m[1]来代替。

At the same time, if you cannot remember which macro would give yield to ‘\n<\c[6]\n[1]\c[0]>’, you can also type out ‘\m[Harold]’ to give way to the same deal as ‘\m[1]’ to write out ‘\n<\c[6]\n[1]\c[0]>’.

如果你记不住ID，你可以用\m[Harold]

**WARNING**

If for some reason you have multiple macros with the same name identifier, then priority will be given to the macro with the lower ID. For example:

如果你有多个重名的，会优先ID最低的

—Macro 10—

	Macro 10 Text Macro 10
	Macro 10 Name abc

—Macro 11—

	Macro 11 Text Macro 11
	Macro 11 Name abc

Here, typing out ‘\m[abc]’ will result in ‘Macro 10’ instead of ‘Macro 11’. This is because the macro name reference ‘abc’ has a lower ID for 10 than 11 does in the macro list.

\m[abc]将会执行—Macro 10—

***
###Instructions – Quick Macros
***

In YEP_X_MessageMacros1.js, there is the option ‘Enable Quick Macro’. If this is set to true, then you can use macros in a quicker fashion. Assuming that this is the setup:

在这个插件里，你可以选择开启快速宏命令。

—Macro 1—

	Macro 1 Text \n<\c[6]\n[1]\c[0]>
	Macro 1 Name Harold

Then ‘\m[1]’ would yield ‘\n<\c[6]\n[1]\c[0]>’. ‘\m[Harold]’ would also yield ‘\n<\c[6]\n[1]\c[0]>’. However, with quick macros enabled, then ‘\Harold’ would also yield  \n<\c[6]\n[1]\c[0]>’ allowing you to type out the macros even faster.

开启快速宏命令，使用\Harold即可实现\m[Harold]的效果

**WARNING**

However, there are some things to keep in mind. If you ever set up a macro that will clash with other text codes, then the macro will take priority over the text code. For example, if you made the quick macro ‘\c’, then all of the color text codes will cease to work as priority is given to the quick macro instead.

这里有些事情需要注意。如果宏命令和文本代码冲突，优先执行文本代码。例如如果你使用了快速宏命令\c，将会设置颜色而不是执行宏

Furthermore, quick macros will give priority to quick macros with lower ID’s than quick macros with higher ID’s if there are similar macro name setups. For example:

如果有相同的名字，快速宏命令优先执行ID低的

—Macro 10—

	Macro 10 Text Macro 10
	Macro 10 Name abc

—Macro 11—

	Macro 11 Text Macro 11
	Macro 11 Name abc123

Typing out ‘\abc123’ will result in ‘Macro 10’ because Macro 10 has ‘\abc’, which contains the first three letters of ‘\abc123’ and has a higher ID than that of ‘\abc’, which then gets the priority.

\abc123优先执行—Macro 10—

***
###Happy RPG Making!


