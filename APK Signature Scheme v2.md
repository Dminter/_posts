---
title: APK Signature Scheme v2 
date: 2017/2/24 9:50:05 
tags:
---
## APK Signature Scheme v2  ##
新的签名方案，提高了app的安装速度，并且对于apk未授权的改变提高了安全性。
相关设置，open the module-level build.gradle file：

	  android {
	    ...
	    defaultConfig { ... }
	    signingConfigs {
	      release {
	        storeFile file("myreleasekey.keystore")
	        storePassword "password"
	        keyAlias "MyReleaseKey"
	        keyPassword "password"
	        v2SigningEnabled false
	      }
	    }
	  }
