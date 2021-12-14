会耗费很长的时间，每次循环的时候都会创建一个新的字符串对象，因为字符串的恒定性
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly53lb14dj309j02uab2.jpg)

NSMutableString是Foundation框架中的一个类，从NSString继承，所以NSMutableString对象是用来存储字符串数据的，NSMutableString在父类NSString的基础之上做了扩展，存储在NSMutableString对象中的字符串数据可以更改，具备可变性

往可变字符串对象中追加字符串【第二个是以拼接的方式追加】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly53s1pjpj30do070acc.jpg)

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly53z5gynj30ac02rgmw.jpg)

NSMutableString从NSString继承，在使用NSString的地方完全可以使用NSMutableString

使用NSMutableString来做大批量的字符串拼接：【NSMutableString只有一个，每次修改的时候直接修改的是这个对象中的数据】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly546qf6vj309a037jsf.jpg)

平时使用NSString，做大量拼接的时候使用NSMutableString