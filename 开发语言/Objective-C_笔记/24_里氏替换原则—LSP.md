子类可以替换父类的位置，并且程序的功能不受影响
```objectivec
Person *p1=[Person new];
Student *s1=[Student new];

Person *p2=[Student new];
```

为什么？
1）父类指针迫切的需求要一个父类对象，而我们给了一个子类对象，这是完全没有问题的【你想要一个人，我给你一个学生】
2）因为父类中拥有的成员子类都有，所以不会影响程序的功能

里氏替换原则的表现形式：
当一个父类指针指向一个子类对象的时候，这里就有里氏替换原则

里氏替换原则的作用：
1）一个指针中不仅可以存储本类对象的地址还可以存储子类对象的地址
2）如果一个指针的类型是NSObject类型的，那么这个指针中可以存储任意的OC对象的地址
3）如果一个数组的元素的类型是一个OC指针类型的，那么这个数组中不仅可以存储本类对象还可以存储子类对象
```
Person *ps[3];

ps[0]=[Person new];
ps[1]=[Student new];
ps[2]=[ItCastStu new];
```

4）如果一个数组的元素是NSObject指针类型，那么意味着任意的OC对象都可以存储到这个数组之中
```
NSObject *objs[4];

objs[0]=[Person new];
objs[1]=[Student new];
objs[2]=[ItCastStu new];
objs[3]=@"jack";
```

5）如果一个方法的参数是一个对象，那么我们在为这个参数传值的时候可以传递一个本类对象，也可以传递一个子类对象，对方法中的代码不会有丝毫的影响
```
God *ys=[God new];

Person *p1=[Person new];
[p1 setName:@"大狗"];

Student *s1=[Student new];
[s1 setName:@"小明"];

ItCastStu *stu=[ItCastStu new];
[stu setName:@"小东"];

[ys killWithPerson:stu];
```

当一个父类指针指向一个子类对象的时候，通过这个父类指针就只能去调用子类对象中的父类成员，子类独有的成员无法访问