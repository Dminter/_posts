---
title: adb_connect.bat
date: 2017-02-14 09:52:11
tags:
---
## adb_connect.bat ##
连接手机WiFi调试，只需输入IP末尾即可

	@echo off
	set /p name=ip-end:
	adb connect 192.168.1.%name%
	pause 

## wifiadb ##
WiFi调试的神器，手机需要root，无需数据线既可完成程序调试
http://www.wandoujia.com/apps/com.ttxapps.wifiadb
