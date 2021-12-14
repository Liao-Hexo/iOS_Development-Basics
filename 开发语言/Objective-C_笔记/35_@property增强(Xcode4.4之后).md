只需要写一个@property，编译器就会自动的
1）生成私有属性
2）生成getter、setter的声明
3）生成getter、setter的实现
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3wfia8pj307j03vaav.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3wm8ffrj30he04dwh7.jpg)

使用注意：
1）@property的类型一定要和属性的类型一致，名称要和属性的名称一致，只是去掉下划线
2）也可以批量声明相同类型的@property
3）@property生成的方法实现没有做任何的逻辑验证
setter：直接赋值
getter：直接返回
所以我么可以重写setter来自定义验证逻辑，如果重写了setter还会自动生成getter，如果重写了getter还会自动生成setter；如果同时重写setter和getter，那么就不会自动生成私有属性了，那么就自己定义一个私有属性就可以了
4）如果你想为类写一个属性，并且为这个属性封装setter和getter，一个@property就搞定
5）父类的@property一样可以被子类继承，@property生成的属性是私有的，在子类的内部无法直接访问生成的私有属性，但是可以通过setter和getter来访问
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3wsxxq1j305m04dt9c.jpg)