---
layout: post
title: UITableView中section展开子菜单的思路
date: 2015-07-07 04:09:00 PM
category: iOS基础
tags: iOS
---
UITableViewCell展开子菜单在实际项目中运用十分广泛。

示例代码：[Demo](https://github.com/rth211/Play_iOS/blob/master/Play_iOS/TVOViewController.m)

* 具体思路如下：

	1.需要声明一个全局BOOL变量isOpen，记录当前cell的展开的状态。

	2.声明一个NSInterge类型selectedIndex，记录选择的cell的section。

	3.点击TableView相应的section的第一行时，展开子菜单。

		- (void)tableView:(UITableView *)tableView didSelectRowAtIndexPath:(NSIndexPath *)
		indexPath{
    	[tableView deselectRowAtIndexPath:indexPath animated:YES];
    	if (_selectedIndex==indexPath.section && _isOpen==YES && indexPath.row==0) {//如果section已经展开，当用户再次在这个section的第一行点击，自动缩回。（indexPath.row==0 保证是第一行）
        	_isOpen=NO;
    	}else{
        	_isOpen=YES;
    	}
    	_selectedIndex=indexPath.section;//记录点击的section
   		[tableView reloadData];//刷新tableview
		}


	4.在tableview的代理中根据_isOpen==YES写入要展开的section的具体子菜单的行数（也就是row的行数）。

				-(NSInteger)tableView:(UITableView *)tableView numberOfRowsInSection:(NSInteger)section
				{
					if (_isOpen==YES ) {
						if (section==_selectedIndex) {
							return x;
							}else{
								return x;
							}
							}else{
								return x;
							}
				}

	>当_isOpen==YES的时候	在被选中的的section中加入row的数目。

	5.在cellForRowAtIndexPath函数中根据_isOpen和__selectedIndex展开需要展开的section。

		-(UITableViewCell *)tableView:(UITableView *)tableView cellForRowAtIndexPath:(NSIndexPath *)indexPath{
    	if (_isOpen==YES ) {//cell展开
        	if (indexPath.section==_selectedIndex) {//被展开的section
            
        	}else{//其他section
           
        	}
    	}else{//UITableViewCell全部没有展开的情况下
    		}
		}
				
