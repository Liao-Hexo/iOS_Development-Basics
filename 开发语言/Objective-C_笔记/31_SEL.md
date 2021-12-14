SEL全称叫做selector选择器，是一个数据类型，所以要在内存中申请空间存储数据

SEL其实是一个类，SEL对象是用来存储一个方法的

如何将方法存储在类对象之中：
1）先创建一个SEL对象
2）将方法的信息存储在这个SEL对象之中
3）再将这个SEL对象作为类对象的属性
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3s7o0v8j30990bv75r.jpg)

因为SEL是一个typedef类型的，在自定义的时候已经加*了，所以我们在声明SEL指针的时候不需要加*
```
SEL s1=@selector(sayHi);
NSLog(@"s1 = %p",s1);
```

### 调用方法的本质：

`[p1 sayHi];`

内部的原理：
1）先拿到存储sayHi方法的SEL对象，也就是拿到存储sayHi方法的SEL数据，SEL消息
2）将这个SEL消息发送给p1对象
3）这个时候，p1对象接收到SEL消息以后，就知道要调用方法
4）根据对象的isa指针找到存储类的类对象
5）找到这个类对象以后，在这个类对象中去搜寻是否有和传入的SEL数据相匹配的，如果有就执行，如果没有再找父类，直到NSObject
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3sgiec7j30iv0bata9.jpg)

OC最重要的一个机制：消息机制，调用方法的本质其实就是为对象发送SEL消息
`[p1 sayHi];`  为p1对象发送一条sayHi消息

手动的为对象发送SEL消息：
1）先得到方法的SEL数据
2）将这个SEL消息发送给p1对象

调用对象的方法，将SEL数据发送给对象：`- (id)performSelector:(SEL)aSelector;`
```objectivec

Person *p1=[Person new];

SEL s1=@selector(sayHi);
[p1 performSelector:s1];

[p1 sayHi];
```

调用一个对象的方法有两种：
1）[对象名 方法名];
2）手动的为对象发送SEL消息

注意：
1）如果方法有参数，那么方法名是带了冒号的
2）如果方法有参数，要传递参数就调用另外一个方法
`* (id)performSelector:(SEL)aSelector withObject:(id)object;`

`* (id)performSelector:(SEL)aSelector withObject:(id)object1 withObject:(id)object2;`
3)如果有多个参数，那就重新创建一个类把多个参数封装进去
```objectivec
Person *p1=[Person new];

SEL s1=@selector(eatWithFood:);
[p1 performSelector:s1 withObject:@"红烧肉"];
```