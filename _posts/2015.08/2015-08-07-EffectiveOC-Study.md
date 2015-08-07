---
layout: post
title: Effective Objective-C 2.0 读书笔记
subtitle:   "Effective系列，值得一看"
date: 2015-08-07 15:11:00
author:     "任天恒"
header-img: "img/home-bg.jpg"
tags:	iOS
---
* 第四十五条：使用dispatch_once来执行只需运行一次的线程安全代码

		+ (id) sharedInstance{
			static EOCClass * sharedInstance=nil;
			static dispatch_once_t onceToken;
			dispatch_once(&onceToken,^{
				sharedInstance = [[self alloc]init];
			});
			return sharedInstance;
		}

	要点：
	1.经常需要编写“只需执行一次的线程安全代码”。通过GCD所提供的dispatch_once函数，很容易能实现次功能。
	2.标记应该声明在static或global作用域中，这样的话，在把只需执行一次的块传给dispatch_once函数时，传进去的标记也是相同的。
