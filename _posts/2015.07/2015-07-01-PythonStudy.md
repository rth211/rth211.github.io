---
layout: post
title: Python笔记
date: 2015-07-01 11:09:00 AM
category: Python基础
tags: Python
---
Python学习之旅，写下这篇笔记，方便以后查看，正所谓“好记性不如烂笔头”。

#1.数据类型

*	变量在声明的时候不需要指定类型
*	数据类型包括：整数（int）、长整数（long）、浮点数（float）和字符串（string）
*	字符串
	使用双引号（"）或者单引号（'），使用print可以打印

	字符串可以使用加号“+”进行连接：	first_name + last_name

	字符串可以使用乘号“*”进行重复： 'hello' * 5

	字符串的操作：strip、count、find、replace
*	列表（list）

	Python内置的一种数据类型是列表:list。list是一种有序的集合，可以随时添加和删除其中的元素。

	如果要取最后一个元素，除了计算索引位置外，还可以用—1做索引，直接获取最后一个元素。（同理-2为倒数第二个）

	**append()**

	向list末尾追加元素。

		>>>classmates.append('Adam')
		>>>classmates
		['Michael', 'Bob', 'Tracy', 'Adam']

	**insert()**

	可以把元素插入到指定的位置，比如索引号为1的位置：

		>>>classmates.insert(1, 'Jack')
		>>>classmates
		['Michael', 'Jack', 'Bob', 'Tracy', 'Adam']

	**pop()**

	删除list末尾的元素

		>>>classmates.pop()
		>>>classmates
		['Michael', 'Jack', 'Bob', 'Tracy']

	**pop(i)**

	删除list中指定位置的元素

*	元组（tuple）

	tuple和list非常类似，但是tuple一旦初始化就不能修改

		>>>classmates = ('Michael', 'Bob', 'Tracy')
		>>>classmates
		('Michael', 'Bob', 'Tracy')

	Q：关于元组和列表的选择？

	A：元组和列表之间存在着诸多相似之处,当要选择创建大量的小列表（包含的项少于12个），后者就会造成内存浪费。

*	字典（dictionary）：

		{"apple":"red","sky":"blue","dirt":"brown"}

*	布尔值： True和False

未完待续~




