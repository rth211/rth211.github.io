---
layout: post
title: Django笔记
date: 2015-07-01 04:15:00 PM
category: Django
tags: Python
---
Django学习之旅，写下这篇笔记，方便以后查看，正所谓“好记性不如烂笔头”。

*	#Django支持的数据库
	1.	PostgreSQL([http://www.postgresql.org/](http://www.postgresql.org/))
	2.	SQLite 3([http://www.sqlite.org/](http://www.sqlite.org/))
	3.	MySQL([http://www.mysql.com/](http://www.mysql.com/))
	4.	Oracle([http://www.oracle.com/](http://www.oracle.com/))

	大部分情况下，这四种数据库都会和Django框架很好的工作。 （一个值得注意的例外是Django的可选GIS支持，它为PostgreSQL提供了强大的功能。）如果你不准备使用一些老旧系统，而且可以自由的选择数据库后端，我们推荐你使用PostgreSQL，它在成本、特性、速度和稳定性方面都做的比较平衡

*	#视图和URL配置

	第一份视图

		from django.http import HttpResponse

		def hello(request):
			return HttpResponse("Hello world")

	代码解析：

	>首先，我们从 django.http 模块导入（import） HttpResponse。
	>
	>接下来，我们定义了一个hello视图函数。
	>
	>每个视图函数至少要有一个参数，通常被叫作request。 这是一个触发这个视图、包含当前Web请求信息的对象，是类django.http.HttpRequest的一个实例。在这个示例中，我们虽然不用request做任何事情，然而它仍必须是这个视图的第一个参数。
	>
	>这个函数只有简单的一行代码： 它仅仅返回一个HttpResponse对象，这个对象包含了文本“Hello world”。

	URLconf

	URLconf就像是Django所支撑网站的目录。它的本质是URL模式以及要位该URL模式调用的视图函数之间的映射表。

	当执行django-admin.py 时，该脚本会自动为你创建一份URLConf（即urls.py）。默认的urls.py会像下面这个样子：

		from django.conf.urls.defaults import *

		# Uncomment the next two lines to enable the admin:
		# from django.contrib import admin
		# admin.autodiscover()

		urlpatterns = patterns('',
    		# Example:
    		# (r'^mysite/', include('mysite.foo.urls')),

    		# Uncomment the admin/doc line below and add 'django.contrib.admindocs'
    		# to INSTALLED_APPS to enable admin documentation:
    		# (r'^admin/doc/', include('django.contrib.admindocs.urls')),

    		# Uncomment the next line to enable the admin:
    		# (r'^admin/', include(admin.site.urls)),
		)

	默认的URLconf包含了一些被注释起来的Django中常用的功能，仅仅只需去掉这些注释就可以开启这些功能. 下面是URLconf中忽略被注释的行后的实际内容	：

		from django.conf.urls.defaults import *

		urlpatterns = patterns('',
		)

	代码解析：

	>第一行导入django.conf.urls.defaults下的所有模块，它们是Django URLconf的基本构造。这包含了一个patterns函数。
	>
	>第二行调用patterns()函数并将返回结果保存到urlpatterns变量。patterns函数当前只有一个参数-一个空的字符串。


	如果想在URLconf中加入URL和view，只需增加映射URL模式和view功能的Python tuple即可. 

		from django.conf.urls.defaults import *
		from mysite.views import hello

			urlpatterns = patterns('',
    		('^hello/$', hello),
		)

	跟原始代码相比，做了两处修改：

	>首先，我们从模块 (在 Python 的 import 语法中， mysite/views.py 转译为 mysite.views ) 中引入了 hello 视图。 （这假设mysite/views.py在你的Python搜索路径上。关于搜索路径的解释，请参照下文。）
	>
	>接下来，我们为urlpatterns加上一行： (‘^hello/$’, hello), 这行被称作URLpattern，它是一个Python的元组。元组中第一个元素是模式匹配字符串（正则表达式）；第二个元素是那个模式将使用的视图函数。

	简单来说，我们只是告诉 Django，所有指向 URL /hello/ 的请求都应由 hello 这个视图函数来处理。












