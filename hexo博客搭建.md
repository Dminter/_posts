---
title: hexo博客搭建
date: 2/14/2017 1:43:35 PM 
tags:
---
## 什么是hexo ##
A fast, simple & powerful blog framework, powered by Node.js. http://hexo.io
## node.js ##
下载安装node.js作为运行环境 https://nodejs.org/en/
## git ##
安装git用作提交博客到github https://git-scm.com/downloads
## github ##
1. 注册github账号，官网https://github.com/
2. 创建个人主页仓库New repository，仓库名为 *xxx.github.io* xxx任意
3. 生成秘钥 在git bash下输入 *ssh-keygen -t rsa -C "Github的注册邮箱地址"* 一直点enter，打开得到的id_rsa.pub，复制内容到https://github.com/settings/keys 新建key粘贴到key里面即可

## hexo ##
	npm install hexo-cli -g
	hexo init blog
	cd blog
	npm install
	hexo server
打开浏览器 http://localhost:4000/ 页面出来了，很帅
## 发布到github ##
打开hexo目录配置文件_config.yml

	deploy:
	  type: git
	  repo: ssh://git@github.com/xxx/xxx.github.io.git
	  branch: master
打开git bash,生成并发布，其间需要输入github账号密码

	npm install hexo-deployer-git --save 【首次需要】
	hexo deploy --generate
	

