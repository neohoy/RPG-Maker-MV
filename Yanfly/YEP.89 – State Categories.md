##YEP.89 – State Categories
***
###Introduction
***
This plugin requires YEP_BuffsStatesCore. Make sure this plugin is located under YEP_BuffsStatesCore in the plugin list.

这个插件需要YEP_BuffsStatesCore，请把它放在YEP_BuffsStatesCore下面

This plugin allows you to set categories for your states. They can be one category, multiple categories, or no categories. With this in mind, there’s a few new features this plugin provides that pertains to this category system such as removal of states under a certain category and the ability to have them bypass certain key removal aspects such as on Death removal or Recover All removal.

这个插件允许你设置状态的分类，他们可以属于一个分类，也可以是多个甚至没有。这样，这个插件就可以提供通过分类来消除状态的功能，或者忽略特定状态，例如死亡自动移除或者全体恢复

***
###Notetags
***
Use the following notetags to alter various properties revolving around state categories for your database objects.

使用下面的标签来设置

####State Notetags:

	<Category: text>
Adds the ‘text’ category to this state. You can insert multiples of this notetag to give a state multiple categories.

设置分类，你可以插入多条此语句来设置多分类

	<Category: Bypass Death Removal>
Adds the ‘Bypass Death Removal’ category to the state. This is a category utilized by the plugin to bypass removal of it upon death.

设置状态忽略死亡

	<Category: Bypass Recover All Removal>
Adds the ‘Bypass Recover All Removal’ category to the state. This is a category utilized by the plugin to bypass removal of it upon using the Recover All event.

设置状态忽略全体恢复效果

####Skill and Item Notetags:

	<Remove State Category: text>
Causes this action to remove all states from category ‘text’ from the action’s target. This will not attempt to remove passive states.

移除分类下的状态

	<Remove x State Category: text>
Causes this action to remove x states from category ‘text’ from the action’s target. The states removed will be the front x states of highest to lowest priority with the matching category text. This will not attempt to remove passive states.

移除分类下的状态x个

***
###Happy RPG Making!