1）@property可以带参数的：@property(参数1，参数2，参数3…..)  数据类型 名称;

@property的四组参数：
1）与多线程相关的两个参数：atomic（默认值）、nonatomic
2）与生成的setter方法的实现相关的参数：assign（默认值）、retain
3）与生成只读、读写相关的参数：readonly、readwrite（默认值）
4）与生成的getter、setter方法名字相关的参数：getter、setter

使用参数注意：
1）同一组参数只能使用一个（getter、setter可以同时使用）
2）参数的顺序可以随意（一般默认顺序就好）


Atomic：如果写atomic，这个时候生成的setter方法的代码就会被加上一把线程安全锁；特点：安全但效率低下
Nonatomic：如果写nonatomic，这个时候生成的setter方法的代码就不会加线程安全锁；特点：不安全但效率高

建议：要效率，选择使用nonatomic



Assign：生成的setter方法的实现就是直接赋值
Retain：生成的setter方法的实现就是标准的MRC内存管理代码，也就是先判断新旧对象是否为同一个对象，如果不是则release旧的，retain新的

当属性的类型是OC对象类型的时候，那么就使用retain
当属性的类型是非OC对象的时候，使用assign

千万注意：retain参数只是生成标准的setter方法为标准的MRC内存管理代码，不会自动的在dealloc中生成release的代码，所以，我们还要自己手动的在dealloc中release




readwrite：代表同时生成getter、setter
readonly：只会生成getter，不会生成setter




默认情况下，@property生成的getter、setter方法的名字都是最标准的名字，其实我们可以通过参数来指定@property生成的方法的名字

getter=getter方法名字，用来指定@property生成的getter方法的名字
setter=setter方法名字，用来指定@property生成的setter方法的名字（注意，setter方法是带参数的，所以要加一个冒号！！）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly45ayietj30b206ewf4.jpg)

如果使用getter、setter修改了生成的方法的名字，在使用点语法的时候，编译器会转换成调用修改后的名字的代码
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly45n8047j302o014wel.jpg)

一般情况下不要去改名字：
1）无论什么情况都不要改setter方法的名字，因为默认情况下生成的名字就已经是最标准的了
2）什么时候修改getter方法的名字：当属性的类型是一个BOOL类型的时候，就修改这个getter的名字以is开头提高代码的阅读性