##Tips & Tricks – Molten Giant – RPG Maker MV

Here’s a neat little trick you can do with the Skill Core plugin: recreate the Molten Giant card from Hearthstone. Its effect is that the card costs less mana depending on how much health the hero is missing. Let’s do that, too, in RPG Maker MV using the Skill Core plugin!

###必备插件：
1. Skill Core

###步骤：
1. 设置技能Molten Giant ，在备注Note里面设置来让掉血量替代MP消耗
<pre>
<Custom MP Cost>
cost -= user.mhp - user.hp
</Custom MP Cost>
</pre>

<pre>
<Custom MP Cost>
cost *= user.hp / user.mhp
</Custom MP Cost>
</pre>