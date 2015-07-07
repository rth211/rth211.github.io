---
layout: post
title: UIView Animation(一)
date: 2015-07-03 02:50:00 PM
category: iOS基础
tags: iOS
---
简单的动画：

	[UIView animateWithDuration: animations:^{} completion:^(BOOL finished) {}];
	[UIView animateWithDuration: animations:^{}];

如果遇到复杂的动画，例如需要组合等等，可以使用：

	[UIView animateWithDuration: delay: options: animations: completion:^(BOOL finished) {}];


*	iOS系统提供的options如下:

		UIViewAnimationOptionLayoutSubviews //提交动画的时候布局子控件，表示子控件将和父控件一同动画。

		UIViewAnimationOptionAllowUserInteraction //动画时允许用户交流，比如触摸

		UIViewAnimationOptionBeginFromCurrentState //从当前状态开始动画

		UIViewAnimationOptionRepeat //动画无限重复

		UIViewAnimationOptionAutoreverse //执行动画回路,前提是设置动画无限重复

		UIViewAnimationOptionOverrideInheritedDuration //忽略外层动画嵌套的执行时间

		UIViewAnimationOptionOverrideInheritedCurve //忽略外层动画嵌套的时间变化曲线

		UIViewAnimationOptionAllowAnimatedContent //通过改变属性和重绘实现动画效果，如果key没有提交动画将使用快照

		UIViewAnimationOptionShowHideTransitionViews //用显隐的方式替代添加移除图层的动画效果

		UIViewAnimationOptionOverrideInheritedOptions //忽略嵌套继承的选项

		//时间函数曲线相关

		UIViewAnimationOptionCurveEaseInOut //时间曲线函数，由慢到快

		UIViewAnimationOptionCurveEaseIn //时间曲线函数，由慢到特别快

		UIViewAnimationOptionCurveEaseOut //时间曲线函数，由快到慢

		UIViewAnimationOptionCurveLinear //时间曲线函数，匀速

		//转场动画相关的

		UIViewAnimationOptionTransitionNone //无转场动画

		UIViewAnimationOptionTransitionFlipFromLeft //转场从左翻转

		UIViewAnimationOptionTransitionFlipFromRight //转场从右翻转

		UIViewAnimationOptionTransitionCurlUp //上卷转场

		UIViewAnimationOptionTransitionCurlDown //下卷转场

		UIViewAnimationOptionTransitionCrossDissolve //转场交叉消失

		UIViewAnimationOptionTransitionFlipFromTop //转场从上翻转

		UIViewAnimationOptionTransitionFlipFromBottom //转场从下翻转
