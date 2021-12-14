让一个类占多个模块，将功能相似的方法定义在同一个模块中
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4dcrtitj30ts0i412s.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4djx97dj30ts0i4wnl.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4dqcc3pj30ts0i4dms.jpg)

分类的使用：如果要访问分类中定义的成员，就要把分类的头文件引进来

分类的作用：
1）将一个类分为多个模块
2）为一个已经存在的类添加方法（扩展一个类）

使用分类的注意事项：
1）分类只能增加方法，不能增加属性
2）在分类之中可以写@property，但是不会自动生成私有属性，也不会自动生成getter、setter的实现，只会生成getter、setter的声明，所以需要自己写getter和setter的实现，也需要自己定义属性，这个属性必须在本类中
3）在分类的方法实现中不可以直接访问本类的真私有属性（定义在本类的@implementation之中，@interface中的可以访问），但是可以通过调用本类的getter和setter来访问属性
4）分类中可以存在和本类同名的方法，当分类中有和本类中同名的方法的时候，优先调用分类的方法，哪怕没有引入分类的头文件；如果多个分类中有相同的方法，优先调用最后编译的分类
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4dy1db4j30qz0avjse.jpg)