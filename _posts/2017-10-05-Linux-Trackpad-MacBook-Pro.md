---
layout: post
title: Trackpad de Macbook Pro con Linux
date: 2017-10-05 14:23:19 -0700
categories: linux macbook pro trackpad touchpad
---

Si estás aquí es porque de seguro instalaste alguna distribución de Linux en tu macbook, y te está volviendo loco el funcionamiento del trackpad o touchpad.
Lo mejor que puedes saber es que no va a mejorar mucho, pero al menos puede ser algo usable.

Lo que se necesita es instalar (en caso de no estar instalado) el paquete mtrack (en debian y Ubuntu el paquete se llama xserver-xorg-input-mtrack). Despues crear un archivo en /etc/X11/xorg.conf.d o modificar /etc/X11/xorg.conf con la siguiente información:

Section "InputClass"
	MatchIsTouchpad "on"
	Identifier		"Touchpads"
	Driver			"mtrack"
	Option			"Sensitivity"	"0.50"
	Option			"FingerHigh"	"12"
	Option			"FingerLow"		"3"
	Option			"IgnoreThumb"	"true"
	Option			"IgnorePalm"	"true"
	Option			"TapButton1"	"1"
	Option			"TapButton2"	"3"
	Option			"TapButton3"	"2"
	Option			"TapButton4"	"0"
	Option			"ButtonEnable"	"true"
	Option			"ButtonMoveEmulate"	"true"
	Option			"ButtonIntegrated"	"true"
	Option			"ClickTime"		"50"
	Option			"ScrollDistance"	"100"
	Option			"TapDragEnable"	"false"
EndSection

Después reiniciar el sistema grafico o el sistema para que los cambios tengan efecto.

La información completa de mtrack así como posibles modificaciones se pueden ver en el [siguiente enlace.](https://github.com/BlueDragonX/xf86-input-mtrack)