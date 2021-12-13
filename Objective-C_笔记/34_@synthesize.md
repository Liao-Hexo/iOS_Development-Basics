作用：自动生成getter、setter方法的实现，所以应该写在类的实现之中

语法：`@synthesize @property名称;`
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3vbvx6cj307005975d.jpg)

@synthesize做的事情：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3vjw8cij307008ign5.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3vqcbuyj30es03u76r.jpg)

问题：
希望@synthesize不要去自动生成私有属性了，getter和setter的实现中操作我们已经写好的属性就可以了

语法：@synthesize @property名称 = 已经存在的属性名;【@synthesize age=_age;】
1）不会再去生成私有属性
2）直接生成setter和getter的实现
Setter的实现：把参数的值直接赋值给指定的属性，是没有做任何逻辑验证的
Getter的实现：直接返回指定的属性的值
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3vxa8p7j305y058q3o.jpg)

如果setter或者getter有自己的逻辑验证，那么就自己在类的实现中重写就可以了

批量声明：
1）如果多个@property的类型一致，可以批量声明

`@property float height,weight;`

2）@synthesize也可以批量声明（类型不一致也可以）

`@synthesize name = _name,age = _age,weight = _weight,height = _height;`