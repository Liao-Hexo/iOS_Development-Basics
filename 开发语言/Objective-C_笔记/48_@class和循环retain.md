当两个类相互包含的时候：Person.h中包含Book.h，而Book.h中又包含Person.h，这个时候就会出现循环引用的问题，就会造成无限递归，而导致无法编译通过

解决方案：
.h头文件：
其中一边不要使用#import引入对方的头文件，而是使用@class 类名；来标注这是一个类，这样子就可以在不引入对方头文件的情况下告诉编译器这是一个类【@class Book;（有分号）】
.m头文件：
在.m文件中再`# import`对方的头文件就可以使用了【#import “Book.h”】(其实不引入也可以，只是会有警告)

@class与@import的区别：
1）#import是将指定的文件的内容拷贝到写指令的地方
2）@class并不会拷贝任何内容，只是告诉编译器这是一个类，这样编译器在编译的时候才可以知道这是一个类



当两个对象相互引用的时候（A对象的属性是B对象，B对象的属性是A对象），这个时候，如果两边都使用retain，那么就会发生内存泄露
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly467uxfuj30db09zdid.jpg)

解决方案：一端使用retain，另外一端使用assign，使用assign的那一端在dealloc中不再需要release了
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly46gdexrj307s04fq40.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly46nkjtpj305606amyc.jpg)

注意：这里有一个很特别的点
[p1 read];要放在[b1 release];之前，否则会出现僵尸对象
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly46ummt7j307n0883zv.jpg)