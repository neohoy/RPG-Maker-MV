
##YEP.111 – Icon Balloons – RPG Maker MV
###Introduction
RPG Maker MV provides us with 15 Balloon Animations to use have to allow our events to show emotions with. Sometimes, this just isn’t enough. However, this plugin allows you to use icons from your IconSet to extend the number of balloon types you can use.

RPG Maker MV提供了我们15个气泡动画来使用，但其实是不够的。现在这个插件可以让你拓展气泡数量

###Plugin Commands

Use these plugin commands to get icon balloons playing on the player/events.

使用下面的插件命令来调整

####Plugin Commands

—

	ShowIconBalloon x on Player
	ShowIconBalloon x on Player, Wait

	ShowIconBalloon x on Event y
	ShowIconBalloon x on Event y, Wait

	ShowIconBalloon x on Follower y
	ShowIconBalloon x on Follower y, Wait
– This will cause the Icon Balloon using icon index x to appear on the player, event y, or follower y. If ‘wait’ is used, then the event will wait until the balloon has finished playing.

可以使用第x位置的图标作为气泡显示在玩家或者事件甚至跟随者身上。如果使用了等待命令，这个事件将会等待气泡播放完毕

—

	ShowIconBalloon x to y on Player
	ShowIconBalloon x to y on Player, Wait

	ShowIconBalloon x to y on Event z
	ShowIconBalloon x to y on Event z, Wait

	ShowIconBalloon x to y on Follower z
	ShowIconBalloon x to y on Follower z, Wait
– This will cause the Icon Balloon start on icon index x and move through to y, the next icon upward each few frames up to icon index y. This icon balloon will be played on the player, event z, or follower z. If ‘wait’ is used, then the event will wait until the balloon has finished playing. When using this command, x cannot be greater than y.

让图标气泡从x变化成y，如果使用这个命令,x的值不能大于y


###Happy RPG Making!

