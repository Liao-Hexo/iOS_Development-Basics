在方法的内部可以定义一个和属性名相同的局部变量，这个时候，如果在方法中访问这个同名的变量，访问的是局部变量，如果需要访问属性就需要使用关键字self

self可以在对象方法和类方法中使用，self是一个指针，在对象方法中self指向当前对象，在类方法中self指向当前类

### self在对象方法中使用：

作用：
1）可以使用self显示的访问当前对象的属性：self->属性，代表访问的是当前对象的这个属性
2）可以使用self来调用当前对象的其他的对象方法

必须使用self的场景：
1）如果在方法中存在和属性同名的局部变量，你如果想要访问同名的局部变量，直接写就可以了，你如果想要访问当前对象的同名属性，必须使用self
2）在对象方法中，如果要调用当前对象的其他的对象方法，必须使用self

属性要求以下划线开头，局部变量不要求以下划线开头，按照这个规范来，实际上是不会重名的

### self在类方法中使用：

self是一个指针，指向当前这个类在代码段中的地址【就相当于这个类】

作用：可以在类方法中使用self来显示的调用本类的其他的类方法

总结取到类在代码段中的地址的方式：
1）调试查看对象的isa指针的值
2）在类方法中查看self的值
3）调用对象的对象方法class，就会返回这个对象所属的类在代码段中的地址
4）调用类的类方法class，就会返回这个类在代码段中的地址
```objectivec
Person *p1=[Person new];

NSLog(@"%p",[p1 class]);
NSLog(@"%p",[Person class]);

```

对象方法可以声明多次，但是只会认为有一次，只能实现一次，否则会报错【对象方法之间是不能重名的；类方法之间也不能重名；但是对象方法和类方法是可以重名的，通过类名来调用，调用的就是类方法，通过对象名来调，调用的就是对象方法】

注意：
1）在对象方法中，self代表当前对象，所以可以通过self访问当前对象的成员，在对象方法中，不能使用self调用本类的类方法
2）在类方法中，self代表当前这个类，所以，可以通过self调用当前类的其他的类方法，在类方法中，不能通过self访问对象的成员，不能直接去访问属性和调用对象的方法