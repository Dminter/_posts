---
title: Android ADB
date: 2017/2/21 14:38:49 
tags:
---
## WiFi调试 ##
手机需要root
手机下载终端模拟器(http://www.coolapk.com/apk/yarolegovich.materialterminal)
输入命令

	su//获取root权限  
	setprop service.adb.tcp.port 5555//设置监听的端口，端口可以自定义，如5554，5555是默认的  
	stop adbd//关闭adbd  
	start adbd//重新启动adbd  

查看手机IP，show WiFi IP Address

	ip -f inet addr show wlan0 
	或者 ifconfig
pc端打开cmd命令行，输入命令 

	adb connect 192.168.1.ip

或者运行如下bat，输入IP即可

	@echo off
	set /p name=ip-end:
	adb connect 192.168.1.%name%
	pause 

## pc连接adb ##
	adb shell
## root权限运行命令 ##
	su
## kill server ##
	adb kill-server
## tcp连接手机 ##
	adb connect #.#.#.#
## 安装apk ##
adb install test.apk
## 卸载apk ##
adb uninstall com.test.app
## 手机传输文件到pc ##
	adb pull /sdcard/demo.mp4 e:\
## pc传输文件到手机 ##
	adb push d:\test.apk /sdcard
## 列出目录下文件 ##
	ls
## 定位到手机目录 ##
	cd /data/data
## 删除文件 ##
	rm -f /sdcard/test.txt
## 创建文件夹 ##
	mkdir /sdcard/tmp
## 当前目录 ##
	pwd
## 复制文件 ##
	cp /sdcard/test.txt /sdcard/demo.txt
## 移动文件 ##
	mv /sdcard/tmp /sdcard/test
## ping ##
	ping www.baidu.com
	PING www.a.shifen.com (58.217.200.13) 56(84) bytes of data.
## 日期 ##
	date
	Tue Feb 21 14:07:24 CST 2017
## 重启手机 ##
	reboot
## Mac地址 ##
	cat/sys/class/net/wlan0/address
	c0:ee:fb:7c:1c:3a
## IP地址 ##
	ifconfig
	或者 ip -f inet addr show wlan0 
## DNS ##
	getprop net.dns1
## 锁屏 ##
	input keyevent 223
## 返回 ##
	input keyevent 3
## 已安装第三方应用 ##
	pm list packages -3
## 已安装应用 ##
	pm list packages 
## 安装路径 ##
	pm path com.google.earth
	cmd=pm.bak path com.google.earth
	package:/data/app/com.google.earth-1/base.apk
## 清除apk数据 ##
	adb shell pm clear com.test.abc
## WiFi密码 ##
	cat /data/misc/wifi/*.config
## 手机电量 ##
	dumpsys battery
## 手机型号 ##
	getprop ro.product.model
## 设备列表 ##
	adb devices
## 截屏 ##
	screencap /sdcard/screen.png
## 录屏 ##
	screenrecord /sdcard/demo.mp4
## 参考网站 ##
> adbshell http://adbshell.com/ 


	