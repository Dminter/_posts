---
title: adb_install.bat
date: 2017-02-14 09:52:11
tags:
---
## adb_install.bat ##
USB连接手机后，安装apk程序到手机，只需要拖放apk到终端即可自动安装

	@echo off
	set /p name=apk-path:
	adb install %name%
	pause 
