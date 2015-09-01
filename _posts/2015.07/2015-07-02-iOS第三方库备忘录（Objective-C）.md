---
layout: post
title: iOS资料收集（Objective-C）
date: 2015-09-01 11:00:00
subtitle:   "整合iOS优秀资料(Objective-C)，包括第三方库，优秀demo"
author:     "任天恒"
header-img: "img/home-bg.jpg"
tags:	iOS
---

*	http
	1.	[AFNetworking](https://github.com/AFNetworking/AFNetworking)，轻量、易用、使用者多、很多开发者在维护中。
	2.	[ASIHTTPRequest](https://github.com/pokeb/asi-http-request)，目前处于年久失修情况。
	3.	[MKNetworkKit](https://github.com/MugunthKumar/MKNetworkKit)，小众产品。
	4.	[RestKit](https://github.com/RestKit/RestKit)，小众产品。

	关于AFN和ASI的对比

	[http://www.infoq.com/cn/articles/afn_vs_asi](http://www.infoq.com/cn/articles/afn_vs_asi)。

*	Socket
	1.	[CocoaAsyncSocket](https://github.com/robbiehanson/CocoaAsyncSocket),大概是最好的了，持异步TCP/UDP，支持GCD，Objective-C接口封装。

*	JSON

	1.	NSJSONSerialization，性能比第三方好，又是官方API(要求：iOS5以上的系统)。
	2.	[JSONKit](https://github.com/johnezang/JSONKit)
	3.	[SBJson](https://github.com/stig/json-framework)

*	实时聊天

	1.	[XMPPFramework](https://github.com/robbiehanson/XMPPFramework)，基于XMPP。
	2.	[SocketRocket](https://github.com/square/SocketRocket)，基于WebSocket。

*	框架类

	1.	[tree20](https://github.com/facebookarchive/three20)，facebook的产品，已废。
	2.	[nimbus](https://github.com/jverkoey/nimbus)，tree20的替代品?
	3.	[BeeFramework](https://github.com/gavinkwoe/BeeFramework)，天朝出品，号称比楼上的产品要好~
	4.	[ReactiveCocoa](https://github.com/ReactiveCocoa/ReactiveCocoa)，函数式和响应式编程，MVVM的思想。
	5.	[react-native](https://github.com/facebook/react-native)，facebook的产品，用JavaScript写iOS程序。
	6.	[Masonry](https://github.com/SnapKit/Masonry)，一款基于官方AutoLayout的iOS自动布局框架，但是比AutoLayout容易使用。
	7.	[samurai-native](https://github.com/hackers-painters/samurai-native),用Html和CSS写iOS程序。
	8.	[DKNightVersion](https://github.com/Draveness/DKNightVersion),白天黑夜切换。

* 测试类框架

	1.	[Kiwi](https://github.com/kiwi-bdd/Kiwi/wiki)
	2.	[specta](https://github.com/specta/specta)
	3.	[cedar](https://github.com/pivotal/cedar)
			[相关文章1](http://www.jianshu.com/p/7e3f197504c1)
			[相关文章2](http://onevcat.com/2014/05/kiwi-mock-stub-test/)

*	数据存储
	1.	[FMDB](https://github.com/ccgus/fmdb)，基于SQLite的存储数据。
	2.	[MagicalRecord](https://github.com/magicalpanda/MagicalRecord)，基于CoreData，用起来更简单，更精简。

*	加载条（ProgressHUD）
	1.	[MBProgressHUD](https://github.com/jdg/MBProgressHUD)
	2.	[SVProgressHUD](https://github.com/TransitApp/SVProgressHUD)

*	网络图片加载
	1.	[SDWebImage](https://github.com/rs/SDWebImage)，异步加载图片，强大的没话说，而且使用简单。
	2.	[FastImageCache](https://github.com/path/FastImageCache)，主要针对于从磁盘文件读取并展示图片的极端优化，并没有集成异步图片下载的功能。
	3.	[Haneke](https://github.com/Haneke/Haneke)
	4.	[PINRemoteImage](https://github.com/pinterest/PINRemoteImage)

	相关资料可以查看：[http://segmentfault.com/a/1190000002776279](http://segmentfault.com/a/1190000002776279)

*	进度条（ProgressView）
	1.	[DDProgressView](https://github.com/ddeville/DDProgressView)
	2.	[THProgressView](https://github.com/tiagomnh/THProgressView)
	3.	[MRProgress](https://github.com/mrackwitz/MRProgress)

*	分段条
	1.	[HMSegmentedControl](https://github.com/HeshamMegid/HMSegmentedControl)
	2.	[NYSegmentedControl](https://github.com/nealyoung/NYSegmentedControl)

*	下拉刷新
	1.	[MJRefresh](https://github.com/CoderMJLee/MJRefresh),强烈推荐使用这个，简单。
	2.	[SVPullToRefresh](https://github.com/samvermette/SVPullToRefresh)
	3.	[EGOTableViewPullRefresh](https://github.com/enormego/EGOTableViewPullRefresh),作者已经停止更新。
	4.	[Pull-to-Refresh.Rentals-iOS](https://github.com/Yalantis/Pull-to-Refresh.Rentals-iOS),带有动画。
	5.	[ODRefreshControl](https://github.com/Sephiroth87/ODRefreshControl),类似于iOS6上的橡皮糖下拉刷新。

*	提示App有新版本
	1.	[Harpy](https://github.com/ArtSabintsev/Harpy)

*	App引导页
	1.	[EAIntroView](https://github.com/ealeksandrov/EAIntroView)

*	开发和调试工具
	1.	[PonyDebugger](https://github.com/square/PonyDebugger)，可以在电脑浏览器上远程调试iOS程序、查看试图层次、网络等等。
	2.	[CocoaLumberjack](https://github.com/CocoaLumberjack/CocoaLumberjack)，一个Log工具，号称是可以提供企业级Log。

*	UILabel
	1.	[TTTAttributedLabel](https://github.com/TTTAttributedLabel/TTTAttributedLabel)，UILabel的改进版。
	2.	[DTCoreText](https://github.com/Cocoanetics/DTCoreText)

*	TextField
	1.	[MMTextFieldEffects](https://github.com/mukyasa/MMTextFieldEffects),15种酷炫自定义TextField。

*	键盘
	1.	[NgKeyboardTracker](https://github.com/meiwin/NgKeyboardTracker),实现类似iMessage中输入框跟随键盘的效果。

*	数字提示框(badgeView)
	1.	[JSBadgeView](https://github.com/JaviSoto/JSBadgeView)
	2.	[RKNotificationHub](https://github.com/cwRichardKim/RKNotificationHub),带有小动画的红字提示框。

*	侧滑栏
	1.	[CDSideBarController](https://github.com/christophedellac/CDSideBarController)
	2.	[REFrostedViewController](https://github.com/romaonthego/REFrostedViewController)
	3.	[RESideMenu](https://github.com/romaonthego/RESideMenu)

* 菜单栏
	1.	[TumblrMenu](https://github.com/cyndibaby905/TumblrMenu),类似于微博点击+号跳出的菜单

* 广告轮播
	1.	[HXInfiniteScrollView](https://github.com/ashamp/HXInfiniteScrollView)
	2.	[SDCycleScrollView](https://github.com/gsdios/SDCycleScrollView)

*	广告卡片
	1.	[iCarousel](https://github.com/nicklockwood/iCarousel)

*	照片选择器
	1.	[MWPhotoBrowser](https://github.com/mwaterfall/MWPhotoBrowser)
	2.	[WSPhotoSheet](https://github.com/PerfectShen/WSPhotoSheet),仿微信的点击选择图片样式。

* AlertView
	1.	[ios-custom-alertview](https://github.com/wimagguc/ios-custom-alertview)

* 提示框
	1.	[Toast](https://github.com/scalessec/Toast),类似于Android的Toast。
	2.	[TAOverlay](https://github.com/TaimurAyaz/TAOverlay)

*	图片生成(可以生成@2x,@3x图片)
	1.	[RTImageAssets](https://github.com/rickytan/RTImageAssets)

* 动画库
	1.	[DGActivityIndicatorView](https://github.com/gontovnik/DGActivityIndicatorView),酷炫的装载动画库及演示。
	2.	[TBIconTransitionKit](https://github.com/AlexeyBelezeko/TBIconTransitionKit),可以很方便的在应用中使用 icon 的点击动画过渡效果。
	3.	[BHBPopView](https://github.com/bb-coder/BHBPopView),仿新浪微博客户端“加号”按钮弹出动画。
	4.	[KYCuteView](https://github.com/KittenYang/KYCuteView),实现类似QQ消息拖拽消失的交互+GameCenter的浮动小球效果。
	5.	[JHChainableAnimations](https://github.com/jhurray/JHChainableAnimations),方便在应用中采用链式写出酷炫的动画效果, 使代码更加清晰易读。
	6.	[SXWaveAnimate](https://github.com/dsxNiubility/SXWaveAnimate),灌水动画。

*	控件
	1.	[Material-Controls-For-iOS](https://github.com/fpt-software/Material-Controls-For-iOS)

*	图表
	1.	[PNChart](https://github.com/kevinzhow/PNChart)
	2.	[TEAChart](https://github.com/xhacker/TEAChart)

*	Model
	1.	[JSONModel](https://github.com/icanzilb/JSONModel)
	2.	[Mantle](https://github.com/Mantle/Mantle)
	3.	[MJExtension](https://github.com/CoderMJLee/MJExtension)

* 模糊效果
	1.	[VVBlurPresentation](https://github.com/onevcat/VVBlurPresentation)

* ActionSheet
	1.	[UICustomActionSheet](https://github.com/pchernovolenko/UICustomActionSheet)

* 跑马灯
	1.	[LSPaomaView](https://github.com/liusen001/LSPaomaView)

*	聊天
	1.	[ZYChat](https://github.com/zyprosoft/ZYChat),聊天界面UI设计思路demo。

*	弹幕
	1.	[QHDanumuDemo](https://github.com/chenqihui/QHDanumuDemo)
	2.	[HJDanmakuDemo](https://github.com/panghaijiao/HJDanmakuDemo)

*	优秀demo
	1.	[仿京东筛选菜单实现](https://github.com/zhangli4659507/JDSelectedDemo)
	2.	[高仿美团](https://github.com/lookingstars/meituan)
	3.	[高仿百度传课](https://github.com/lookingstars/chuanke)
	4.	[高仿土豆](https://github.com/lookingstars/tudou)
	5.	[高仿遨游](https://github.com/lookingstars/aoyouHH)
	6.	[高仿美团iPad版](https://github.com/aiqiuqiu/Tuan)
	7.	[v2ex](https://github.com/singro/v2ex)
	8.	[豆瓣FM](https://github.com/XVXVXXX/DoubanFM)
	9.	[高仿One](https://github.com/ihappyhacking/MyOne-iOS)
	10.	[高仿网易](https://github.com/dsxNiubility/SXNews)
	11. [高仿城觅](https://github.com/ZhongTaoTian/WNXHuntForCity)
	12.	[仿微信聊天](XMChatBarExample)

*	iOS学习资料汇总
	1.	[trip-to-iOS](https://github.com/Aufree/trip-to-iOS)
	2.	[iOS动画资料](https://github.com/cjwirth/awesome-ios-ui)
	3.	[iOS中的开发字体](https://github.com/dsxNiubility/SXFontShow)
