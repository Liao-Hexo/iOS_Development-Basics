1）NSString是一个数据类型，用来保存OC字符串
2）NSString是Foundation框架中的一个类，作用是存储OC字符串的，所以OC中的字符串本质上是用NSString对象来存储的

其实完整的标准的创建NSString对象的方式：
NSString *str0=[NSString new];
NSString *str1=[NSString string];
这种方式创建的字符串是空字符串 @“”

但是，NSString是我们最常用的一个对象，所以OC使用了一种更为简单的方式来创建字符串对象：直接使用@来表示一个OC字符串
@“jack”;(这个其实本质上是一个NSString对象)

NSString *str=@“jack”;【str的值是这个对象的地址，%p打印的是指针变量的值；%@打印的是指针变量指向的对象】
NSString *str1=[NSString stringWithFormat:@“jack”];

- - - -

NSString最常用的类方法：

1. `+ (instancetype)stringWithUTF8String:(const char *)nullTerminatedCString;`
Instancetype作为返回值，代表返回的是当前这个类的对象
作用：将C语言的字符串转换为OC字符串对象

2. `+ (instancetype)stringWithFormat:(NSString *)format,….`
作用：拼接一个字符串对象，使用变量或者其他数据拼接成OC字符串
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3llywhfj30hj05ctav.jpg)

- - - -

NSString最常用的对象方法：

1. length方法，返回值为NSUInteger，其实就是unsigned long
得到字符串的字符的个数，可以处理中文
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3lx9vl5j308x044myd.jpg)

2. 得到字符串中指定下标的字符
`* (unichar)characterAtIndex:(NSUInteger)index;`
返回值是unichar，其实就是unsinged short，占据两个字节

如果要输出unichar变量的值使用%C(中文输出)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3m5g3snj309h04ldh3.jpg)

3. 判断两个字符串的内容是否相同，不要用==去判断，因为这样有可能会出问题：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3me1e4aj30co06ywgl.jpg)

判断相等的方式：
`* (BOOL)isEqualToString:(NSString *)aString;`
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3mkylqvj30cr0900v4.jpg)

4. 比较字符串的大小

`* (NSComparisonResult)compare:(NSString *)string;`
完全可以使用int来接收结果，因为返回值是一个枚举
返回值如果是-1（小于），0（等于），1（大于）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3ms9hzuj308o054gn3.jpg)