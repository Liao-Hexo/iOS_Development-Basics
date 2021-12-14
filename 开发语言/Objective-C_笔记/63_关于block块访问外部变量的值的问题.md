1）在block代码块的内部可以取定义在外部的变量的值，包括定义在外部的局部变量和全局变量
2）在block代码块的内部可以修改全局变量的值，但是不能修改定义在外部的局部变量的值
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4l9a64rj307v091mz1.jpg)
3）如果你希望我们定义的局部变量可以允许在block代码的内部去修改，那么就为这个局部变量加一个__block(两个下划线)的修饰符
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4lhnhysj307v01c0sv.jpg)