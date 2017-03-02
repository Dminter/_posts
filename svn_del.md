---
title: svn_del.reg
date: 2017-02-14 09:52:11
tags:
---
## svn_del.reg ##
双击，添加到注册表，之后再SVN目录下右键选择即可删除该目录下带.svn的文件

	Windows Registry Editor Version 5.00
	
	[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Folder\shell\DeleteSVN]
	@="Delete SVN Folders"
	
	[HKEY_LOCAL_MACHINE\SOFTWARE\Classes\Folder\shell\DeleteSVN\command]
	@="cmd.exe /c \"TITLE Removing SVN Folders in %1 && COLOR 9A && FOR /r \"%1\" %%f IN (.svn) DO RD /s /q \"%%f\" \""