---
title: adb_push.bat
date: 2017-02-14 09:52:11
tags:
---
复制文件到手机，需要事先在手机sdcard建立文件夹1，USB连接手机，之后直接拖放文件到终端即可

	@echo off
	set /p name=file-path:
	adb push %name% /sdcard/1
	pause 
