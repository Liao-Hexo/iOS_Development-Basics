在ARC的机制下，@property参数不能使用retain，因为retain代表生成的setter方法是MRC的标准内存管理代码

ARC机制下关注的重点：当一个类的属性是一个OC对象的时候，这个属性应该声明为强类型的还是弱类型的，很明显应该声明为强类型的
【人未死车已报废】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly49rp7k7j307i05lwfd.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly49yxjnzj307i04gaax.jpg)

如何控制@property生成的私有属性是一个强类型的还是一个弱类型的？
使用参数：strong（默认值）和weak
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4a5pjxxj30700173yw.jpg)

使用建议：
1）在ARC机制下，如果属性的类型是OC对象类型的，绝大多数场景下使用strong
2）在ARC机制下，如果属性的类型不是OC对象类型的，使用assign
3）strong和weak都是应用在属性的类型是OC对象的时候