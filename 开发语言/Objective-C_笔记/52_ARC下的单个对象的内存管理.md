1）当指向对象的所有的强指针被回收的时候，对象就会被立即回收
2）当所有指向对象的强指针赋值为nil的时候，对象就会被立即回收

注意：不能创建对象用一个弱指针存储这个对象的指针，这样的话，刚创建出来的对象，就没有任何强指针指向，创建出来就被回收
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly48zujqsj309504rdh8.jpg)

在ARC机制下，当对象被回收的时候，原来指向这个对象的弱指针会被自动设置为nil
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4988ujuj309w09a401.jpg)