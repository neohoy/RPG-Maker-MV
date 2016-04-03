##YEP.88 – Picture Common Events
***
###introduction
***

Pictures can function as something other than just a visual for your game. They can sometimes serve as UI elements or more! However, what they don’t have the ability to inherently do is to call upon common events when clicked on by the mouse. With this plugin, the pictures bound to a common event will become usable when clicked or touched!

图片不仅仅可以作为图像存在你的游戏，还可以实现很多功能。他们可以用来做界面元素。可可目前他们还不能在鼠标点击时作为公共事件执行。使用这个插件，图片可以绑定公共事件，当鼠标点击或者触摸时执行

***
###Instructions
***

In the plugin’s parameters, you can set common event ID’s to each picture ID listed from 1 to 100 (max number of pictures used in RPG Maker MV is 100). If the picture is has even a value of 1 opacity, that picture can be used for a common event. There are four condition types that can be bound with the common events:

在插件参数里，你可以绑定图片的事件ID，总共图片上限100张。只要图片有值，他就会用于事件。这里有4种触发情况

—

– CLICK –  
If the picture is clicked upon, this will prompt the common event to trigger if the common event value listed is above 0. This will trigger only once until the player releases the mouse (or stops touching the screen).

点击：当图片被单击时触发。事件需要玩家点击鼠标并释放后才触发

– REPEAT –  
If the mouse is clicked and then held (or if the touch screen is pushed and held), as long as the mouse is above the picture area and the common event value listed is above 0, then this will trigger once every 6 frames until the player releases the mouse (or stops touching the screen) or moves the mouse outside of the picture boundaries.

重复：如果鼠标按下并不放松，在释放之前，每6帧就会执行一次

– HOLD –  
If the mouse is clicked and then held (or if the touch screen is pushed and held), as long as the mouse is above the picture area and the common event value listed is above 0, then this will trigger every frame until the player releases the mouse (or stops touching the screen) or moves the mouse outside of the picture boundaries.

按住：如果鼠标按下并且不放松。在释放之前，每帧都会执行一次

– RELEASE –  
Upon releasing the clicked mouse (or the moment the player stops touching the screen) and releases the mouse above this picture and if the picture’s common event value listed is above 0, then this will trigger upon release.

释放：鼠标放松时触发

—

Note that there are some behavioral changes in regards to pictures bound to that of common events. Any picture that’s bound to a common event will be separate from the map’s spriteset, and instead, bound to the scene. This is so that in the event the screen is scrolled, zoomed in, shakes, etc., it will NOT affect the bound pictures.

注意地图的放大，移动，震动等不会影响绑定图片

This is because the pictures are generally to be used as UI elements and UI elements best work under the practice that they do not change position.

因为图片已经作为界面元素产生，不会改变位置

***
###Plugin Commands
***

The following are some plugin commands you can use should you want to add a bit of control with the Picture Common Events.

下面插件命令可以用来控制图片事件

####Plugin Command

	EnableTouchMove
	DisableTouchMove
– Allows the player to press a destination on the screen and move there or disables the player from using touch movement.

允许玩家触碰来移动

	HidePictureCommonEvents
	ShowPictureCommonEvents
– Manually hide all pictures bound to common events or show them. If shown then pictures will return to their previous opacity value. Hidden pictures cannot be triggered to activate common events.

显示和隐藏图片事件

	MovePlayer Down
	MovePlayer Left
	MovePlayer Right
	MovePlayer Up
– Will cause the player character to move as if moving by using a 4-dir input (either via keyboard or controller). This is best used with ‘Press’.

使玩家移动

	TriggerButton Ok
	TriggerButton Cancel
	TriggerButton Dash
	TriggerButton PageUp
	TriggerButton PageDown
	TriggerButton Left
	TriggerButton Up
	TriggerButton Right
	TriggerButton Down
– This will cause the game to simulate triggering the button command of one of those original functions even if there is a common event bound to all of the keys of that original function.

绑定按钮按键

***
###Happy RPG Making!

