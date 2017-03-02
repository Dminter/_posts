---
title: Android tips
date: 2017/2/21 11:28:30 
tags:
---
## edittext默认不弹出键盘 ##
只需要上层view获取焦点即可

      android:focusable="true"
      android:focusableInTouchMode="true"

## performClick ##
使用代码模拟控件点击事件

	performClick -view’s OnClickListener

