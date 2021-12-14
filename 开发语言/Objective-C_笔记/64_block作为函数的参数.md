定义：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4m5ef33j307v05xta6.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4maxin7j307v05x402.jpg)

调用：
1）如果要调用的函数的参数是block类型的，那么要求在调用的时候传入一个和形参block要求的代码段
2）调用的时候，可以先将代码段存储到一个block变量中，然后再传递这个block变量；也可以直接将符合要求的代码段写在小括弧中传递
3）小技巧：通过Xcode提示可以快速的生成block代码段的框架
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4mhp6yxj30860cj0v8.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4mq35tjj30et0brtbg.jpg)

将block作为函数的参数可以实现什么效果：可以将调用者自己写的一段代码传递到函数的内部去执行