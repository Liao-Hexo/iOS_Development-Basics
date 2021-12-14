1）可以用在类方法和对象方法之中

2）在对象方法中可以使用super关键字调用当前对象从父类继承过来的对象方法
```objectivec
[self sayHi];
[super sayHi];
```

3）在类方法中，super关键字可以调用当前类从父类继承过来的类方法【类方法也能被子类继承，父类中的类方法可以使用父类名来调用，也可以使用子类名调用】
```objectivec
[Person hehe];
[Student hehe];
[self hehe];
[super hehe];
```

4）super只能用来调用父类的对象方法或者类方法，不能用来访问属性