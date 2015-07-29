---
layout: post
title: 胖Model和瘦Model
subtitle: "胖model和瘦model（fat model，skinny controller）"
date: 2015-06-30 09:21:00
author: "任天恒"
header-img: "img/home-bg.jpg"
tags: iOS
---

胖model和瘦model（fat model，skinny controller）

1.胖model：

胖model包含了部分弱业务逻辑。胖model需要达到的目的是，Controller从胖Model这里拿到数据之后，不用额外做操作或者只要做非常少的操作，就能够将数据直接应用在view上。举个例子：

**Raw Data:**

    timestamp:1234567

**FatModel:**

    @property (nonatomic, assign) CGFloat timestamp;
    - (NSString *)ymdDateString; // 2015-04-20 15:16
    - (NSString *)gapString; // 3分钟前、1小时前、一天前、2015-3-13 12:34

**Controller:**

    self.dateLabel.text = [FatModel ymdDateString];
    self.gapLabel.text = [FatModel gapString];

把timestamp转换成具体业务上所需要的字符串，这属于业务代码，算是弱业务。FatModel做了这些弱业务之后，Controller就变得非常skinny，Controller只需要关注强业务代码就行。众所周知，强业务变动的可能性要比弱业务大得多，弱业务相对稳定，所以弱业务塞进Model里面是没问题的。另一方面，弱业务重复出现的频率大于强业务，对复用性的要求更高，如果这部分业务写在Controoler，类似的代码会洒的到处都是，一旦弱业务有修改（弱业务修改平率低不代表就没有修改），这个事情就是一个灾难。如果塞到Model里面去，改一改很多地方就都能跟着改，就能避免这场灾难。

然后其缺点就在于，胖Model相对比较难移植，虽然只是包含弱业务，但好歹也是业务，迁移的时候容易拔出萝卜带出泥。另外一点，MVC的架构思想更倾向于Model是一个Layer，而不是一个Object，不应该把一个layer应该做的事情交给一个Object去做。最后一点，软件是会成长的，FatModel很有可能随着软件的成长越来越Fat，最终难以维护。

2.瘦Model

瘦Mode只负责业务数据的表达，所有业务无论强弱一律扔到Controller。瘦Model要达到的目的是，尽一起可能去编写细粒度Model，然后配套各种helper类或方法来弱业务做抽象，强业务依旧交给Controller。

**Raw Data:**


    "name":"casa",
    "sex":"male",


**SlimModel:**

    @property (nonatomic, strong) NSString *name;
    @property (nonatomic, strong) NSString *sex;

**Helper:**

    #define Male 1;
    #define Female 0;
    + (BOOL)sexWithString:(NSString *)sex;

**Controller:**

    if ([Helper sexWithString:SlimModel.sex] == Male) {
        ...
    }

由于SlimModel跟业务完全无关，它的数据可以交给任何一个能处理它数据的Helper或其他的对象，来完成业务。在代码迁移的时候独立性很强，很少会出现拔出萝卜带出泥的情况。另外，由于SlimModel只是数据表达，对它进行维护基本上是0成本，软件膨胀得再厉害，SlimModel也不会大到哪儿去。

缺点就在于，Helper这种做法也不见得很好，这里有一篇文章批判了这个事情。另外，由于Model的操作会出现在各种地方，SlimModel在一定程度上违背了DRY（Don't Repeat Yourself）的思路，Controller仍然不可避免在一定程度上出现代码膨胀。

说回来，MVCS是基于瘦Model的一种架构思路，把原本Model要做的很多事情中的其中一部分关于数据存储的代码抽象成了Store，在一定程度上降低了Controller的压力。
