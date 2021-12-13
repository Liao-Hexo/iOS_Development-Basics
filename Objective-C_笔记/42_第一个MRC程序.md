要写MRC的程序，必须先把Xcode默认的ARC模式关闭，开启MRC

在ARC机制下，retain，release，dealloc这些方法无法调用
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly41osfo1j30m40lkgo4.jpg)

重写dealloc方法的规范：
必须要调用父类的dealloc方法，并且要放在最后一句代码

测试引用数据：
1）新创建一个对象，这个对象的引用计数器的值默认是1
2）当对象的引用计数器变为0的时候，对象就会被系统立即回收，并自动调用dealloc方法
3）为对象发送retain消息，对象的引用计数器就会+1
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly41xz6fwj30dc0bw42n.jpg)

为对象发送release消息，并不是回收对象，而是让对象的引用计数器-1，当对象的引用计数器的值变为0的时候，对象才会被系统立即回收