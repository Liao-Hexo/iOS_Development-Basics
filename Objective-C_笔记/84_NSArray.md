是Foundation框架中的一个类，这个类的对象是来存储多个数据的，具备数组的功能，所以NSArray是OC中的数组
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly54r5m1kj30bk029q3z.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly54y4dt3j30am02sjsl.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly554f48oj309n04n75b.jpg)
最常用的创建数组的方式：【只能存储OC对象】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly55biuvaj30f906jdha.jpg)
简写方式：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly55i1ayhj308n05gab6.jpg)

取出对应的元素的值：
1）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly55ou6yzj3085073gna.jpg)
2）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly55v4cuuj308505u0u3.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly561562gj30ax02b0tp.jpg)

NSArray数组的其他常用方法：
1）得到数组中元素的个数
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly568u6knj309r05utae.jpg)
2）判断数组中是否包含指定的元素
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly56fpr1qj309r08qtav.jpg)
3）查找指定的元素在NSArray数组中第一次出现的下标
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly56mqmepj30bc01pdgl.jpg)

NSArray数组的遍历：
1）使用for循环
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly56ua7zxj30bc06vdii.jpg)
2）声明在for()中的变量叫做迭代变量【执行原理：将数组中的第一个元素的值赋值给迭代变量，执行循环体，再将数组中的第二个元素的值赋值给迭代变量，再执行循环体】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly571nnsbj30bc06vgo9.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly577p421j30bc092q5y.jpg)
 3）使用block遍历
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly57ef4cnj30ef08042f.jpg)