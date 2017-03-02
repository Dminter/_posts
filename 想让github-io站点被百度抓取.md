---
title: 想让github-io站点被百度抓取
date: 2/17/2017 11:01:23 AM 
tags:
---
## 测试自己网站有无被抓取 ##
![](http://i.imgur.com/uNxP99w.png)
没有，就到百度站长平台 http://zhanzhang.baidu.com 去添加自己网站，添加百度的meta标签到Hexo/themes/next/layout/_partials
目录下的head.swig中，测试
	
	抓取诊断 >	抓取详情
	以下是百度Spider抓取结果及页面信息：
	提交网址：	http://dminter.github.io/2017/02/14/retrofit/
	抓取网址：	http://dminter.github.io/2017/02/14/retrofit/
	抓取UA：	Mozilla/5.0 (compatible; Baiduspider/2.0; +http://www.baidu.com/search/spider.html)
	抓取时间：	2017-02-17 10:49:34
	网站IP：	151.***.***.133 报错
	下载时长：	0.367秒
	抓取异常信息：	拒绝访问  查看帮助 
	返回HTTP头：
	HTTP/1.1 403 Forbidden
	Cache-Control: no-cache
	Content-Type: text/html
	Transfer-Encoding: chunked
	Accept-Ranges: bytes
	Date: Fri, 17 Feb 2017 02:49:35 GMT
	Via: 1.1 varnish
	Connection: close
	X-Served-By: cache-itm7425-ITM
	X-Cache: MISS
	X-Cache-Hits: 0
	X-Timer: S1487299775.735600,VS0,VE186
	Vary: Accept-Encoding
	X-Fastly-Request-ID: c5c6bf1d17ec9f437bdaec2963af560b878c9f58

显然不可行，原因是GitHub拒绝了百度爬虫，原因可想而知，网上也有其他办法解决，但是提交网站让百度主动抓取的方法已略知一二了。
