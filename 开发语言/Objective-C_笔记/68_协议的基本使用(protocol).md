作用：专门用来声明一大堆方法（不能声明属性，也不能实现方法，只能用来写方法的声明），只要某个类遵守了这个协议，就相当于拥有这个协议中的所有的方法声明，而不用自己去定义

协议的声明：

@protocol 协议名称 <NSObject>

方法的声明;

@end
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4pbw8nij30ku06smzn.jpg)

在协议中，只能用来声明方法，就是专门用来写方法声明的，就是用来被类遵守的

如果想要让一个类拥有协议中定义的所有的方法声明，那么就让这个类遵守这个协议，类只要遵守一个协议，那么这个类就拥有了这个协议中定义的所有的方法的声明

@interface 类名 ： 父类名 <协议名称>

@end

：表示继承
<>表示遵守的协议

这个类只是拥有了这个协议中的方法的声明而已，没有实现，所以这个类还应该实现协议中的方法

如果类不实现协议中的方法，其实也不会报错，编译器只是会报警告；但是当创建对象，来调用这个没有实现的协议中的方法的时候，就会报错


类是单继承，但是协议可以多遵守
@interface 类名：父类名 <协议名称1，协议名称2……>

@end