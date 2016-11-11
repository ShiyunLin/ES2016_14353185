# lab3-DOL实例分析

### 1.修改example2,将square由3个变2个

	#### i. 修改后的*.dot图

 ![屏幕快照 2016-11-10 下午9.43.29](/Users/shiyunlin/Desktop/lab3-dol-example/lab3_dol_pictures/屏幕快照 2016-11-10 下午9.43.29.png)

#### ii. 修改后的运行截图：

 ![屏幕快照 2016-11-10 下午9.30.55](/Users/shiyunlin/Desktop/lab3-dol-example/lab3_dol_pictures/屏幕快照 2016-11-10 下午9.30.55.png)



#### iii.修改方法：

在example2.xml中，修改iterator中定义的迭代次数，里面有一个迭代value值，在这里将3改成2即可。



### 2.修改example1,将平方结果变成立方

#### i. 修改后的*.dot图（没有修改square的名字，这里显示还是平方，但实现是立方）

 ![屏幕快照 2016-11-10 下午9.42.58](/Users/shiyunlin/Desktop/lab3-dol-example/lab3_dol_pictures/屏幕快照 2016-11-10 下午9.42.58.png)



#### ii. 修改后的运行截屏

 ![屏幕快照 2016-11-10 下午9.20.08](/Users/shiyunlin/Desktop/lab3-dol-example/lab3_dol_pictures/屏幕快照 2016-11-10 下午9.20.08.png)



#### iii. 修改方法：

在square.c中，实现平方的函数中，返回两个i相乘改成  "i* i *i"。