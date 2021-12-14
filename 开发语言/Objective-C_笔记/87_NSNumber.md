无论是NSArray还是NSMutableArray里面都只能存储OC对象，基本数据类型是无法存储的

NSNumber是Foundation框架中定义好的一个类，这个类的对象的作用就是用来包装基本数据类型的
1）先将基本数据类型包装到NSNumber对象中
2）再将NSNumber对象存储到NSArray数组中
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5bbtua2j308v04tdhg.jpg)

简写方式：
【@10代表是一个NSNumber对象，这个对象中包装的是整型的10】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5bj7seij306i02rmxu.jpg)

如果后面的数据是一个变量，那么这个变量就必须要使用小括弧括起来：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5bph0vzj304z02074e.jpg)