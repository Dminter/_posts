---
title: gradle errors logs
date: 2017-02-28 09:52:11
tags:
---
## Manifest merger failed with multiple errors, see logs ##
	C:\dminter\co\workspace\MMLibrary\app\src\main\AndroidManifest.xml:133:5-75 Warning:
		Element uses-permission#android.permission.DISABLE_KEYGUARD at AndroidManifest.xml:133:5-75 duplicated with element declared at AndroidManifest.xml:6:5-75
	
	C:\dminter\co\workspace\MMLibrary\app\src\main\AndroidManifest.xml Error:
		uses-sdk:minSdkVersion 15 cannot be smaller than version 16 declared in library [com.github.CarGuo:GSYVideoPlayer:v1.6.0] C:\dminter\co\workspace\MMLibrary\app\build\intermediates\exploded-aar\com.github.CarGuo\GSYVideoPlayer\v1.6.0\AndroidManifest.xml
		Suggestion: use tools:overrideLibrary="com.shuyu.gsyvideoplayer" to force usage
	
	
	See http://g.co/androidstudio/manifest-merger for more information about the manifest merger.
	
	:app:processDebugManifest FAILED
	
	FAILURE: Build failed with an exception.
	
	* What went wrong:
	Execution failed for task ':app:processDebugManifest'.
	> Manifest merger failed with multiple errors, see logs
	
	* Try:
	Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output.
	
	BUILD FAILED
	
	Total time: 3.728 secs

	解决办法，在主AndroidManifest文件里面加入
	<uses-sdk tools:overrideLibrary="com.shuyu.gsyvideoplayer"/>