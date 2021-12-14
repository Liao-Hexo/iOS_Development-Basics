NSString是一个数据类型，保存OC字符串的，实际上NSString的本质是一个类
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4rhv2ywj3081022756.jpg)
使用这种方式创建的字符串是一个空的字符@“”

当我们调用NSString的类方法来创建对象的时候，创建的字符串对象是存储在堆区

OC提供了一种更为快速的创建字符串对象的方式，使用前缀@

@“jack”;
本质上这是一个NSString对象，这个NSString对象中存储的是”jack”这个字符串，这个字符串对象是存储在常量区（数据段）的

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4rpku0sj30gi096mye.jpg)

NSString的恒定性：当在内存中创建一个字符串对象以后，这个字符串对象的内容就无法更改，当我们重新为字符串指针初始化值的时候，并不是修改原来的字符串对象，而是重新的创建一个字符串对象，将这个字符串对象的地址重新赋值给字符串指针变量
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4rxdc8kj30eg0ae756.jpg)

当系统准备要在内存中创建字符串对象的时候，会先检查内存中是否有相同内容的字符串对象，如果有直接指向，如果没有才会重新创建

存储在常量区的数据不会被回收，所以存储在常量区的字符串对象也不会被回收【堆区也一样】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4s4r2d6j30ck08tdjc.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4scarf2j30dj09i77o.jpg)