NSObject是OC中所有类的基类，根据LSP，NSObject指针就可以指向任意的OC对象，所以，NSObject指针是一个万能指针，可以指向任意的OC对象

缺点：如果要调用指向的子类对象的独有的方法，就必须要做类型转换
```
NSObject *obj1=[Person new];
[(Person *)obj1 sayHi];

NSObject *obj2=[Student new];
[(Student *)obj2 study];

NSObject *obj3=@"jack";
[(NSString *)obj3 length];
```

id指针：是一个万能指针，可以指向任意的OC对象

id是一个typedef自定义类型，在定义的时候已经加了*，所以，声明id指针的时候不需要再加*了

通过NSObject指针去调用对象的方法的时候，编译器会做编译检查
通过id类型的指针去调用对象的方法的时候，编译器直接通过，无论你调用什么方法【该运行错误的还是运行错误】

注意：id指针只能调用对象的方法，不能使用点语法，如果使用点语法就会直接报编译错误

如果我们要声明一个万能指针，不要使用NSObject，而是使用id

