无论在MRC还是ARC下，如果属性的类型是NSString类型的，@property参数使用copy

Copy是一个方法，定义在NSObject类之中，作用是拷贝对象

没有产生新对象，而是直接将对象本身的地址返回，这种拷贝我们叫做浅拷贝：【拷贝出来的是不可变字符串对象】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5q0qv3tj306q04hq40.jpg)

有产生一个新对象，这样的拷贝我们叫做深拷贝
【是一个不可变的字符串对象】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5q7luchj30d904habq.jpg)

mutableCopy：定义在NSObject类之中，作用是拷贝对象

可变字符串对象，深拷贝：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5qh8mp5j309304habj.jpg)

可变字符串对象，深拷贝：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5qnexwjj30cz04e40c.jpg)

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5qtfylfj30i401bq4a.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5qzota7j30b301bgma.jpg)

若字符串对象存储在常量区中，存储在常量区的数据是不允许被回收的，所以存储在常量区的字符串对象的引用计数器是一个很大的数，并且retain和release无效
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5r7iivlj30bi05ddhh.jpg)
若字符串存储在堆区，这个字符串对象和普通的对象是一样的，引用计数器默认是1
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5rg0qtpj30hn09e76v.jpg)

字符串对象如果是浅拷贝，会将对象的引用计数器+1；如果是深拷贝，原来的对象的引用计数器不变，新拷贝出来的对象的引用计数器为1
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5rn5qvoj30gz07racr.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5rtvicaj30gz091422.jpg)


1）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5s0mmywj30aj08k0u6.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5s772gjj30gl0ceq4y.jpg)
2）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5seqqloj30cw082gnh.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5skon20j30gy0bvtar.jpg)
3）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5srfi3rj308p06j0u2.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5syxinyj306i05b0to.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5t4ha35j30d908swh9.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5tb70nsj30fn0cb777.jpg)

Copy方法的确是定义在NSObject类中的一个方法，但是copy方法的内部还调用了另外一个方法：copyWithZone，这个方法是定义在NSCoping协议之中的，因为我们的类没有遵守这个协议，所以当我们自定义的类调用copy方法的时候就会出错
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5tjhrdtj308p06jq3z.jpg)

解决方案：【return self;就是浅拷贝了】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5trimc8j30cr02nmyr.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5txruhkj308p03v0tu.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5u3ddrej30dv07awgb.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5uarq3oj30dv099acu.jpg)