---
title: hexo无法上传到github
date: 2017-02-14 09:52:11
tags:
---
    init script '/dev/tty: No such device or address' error on redirect

处理办法

	deploy:
	  type: git
	  repo: ssh://git@github.com/Dminter/dminter.github.io.git
	  branch: master
