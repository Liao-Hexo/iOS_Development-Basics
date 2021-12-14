NSArray与NSMutableArray的缺点：数组元素的下标不固定，都有可能会发生变化，无法通过下标来唯一确定数组中的元素

存储数据的时候，必须要为存储的数据取一个别名，这个别名的作用就是用来确定别名对应的数据的，这种存储数据的方式就叫做键值对的存储方式（Key-Value）

它们是数组，是以键值对的形式存储数据的，往这个数组中存储数据的同时必须要指定这个数据的别名才可以，要找到存储在这个数组中的数据，通过别名来找，而不是通过下标

NSDictionary：字典数组
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5c9eceqj30ar027my6.jpg)

创建字典数组：
1）这种方式无意义
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5cgt98qj309901raas.jpg)
2）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5cmnc6zj30gb018gma.jpg)
3）简要方式
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5ct29xbj30gb0183z1.jpg)

使用：
1）根据别名取值：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5d0yy6ij30dd01qwep.jpg)
2）键值对的数量：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5d7cblej30dd01q0sv.jpg)
3）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5ddq3fwj308002ajrl.jpg)
4）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5djk64yj309302amxd.jpg)
5）遍历字典数组【字典数组中的数据无法使用下标去取，所以普通的for循环就无用了】

1.使用for in循环遍历出来的是字典数组中所有的键，再通过键取出对应的值
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5dqj0frj30ax0b4gov.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5dxr6l8j30eq097dj6.jpg)
2.使用block遍历
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5e6jq5cj30ix0c442y.jpg)

字典数组存储数据的原理：
1）并不是按照顺序依次存储的
2）存储键值对的时候，会根据键和数组的长度做一个哈希算法，算出一个下标，将这个键值对存储在该下标处
3）取值的时候也是做哈希算法

与NSArray对比：
1）NSArray数组的元素是按照顺序来存储的，字典数组中存储的下标是算出来的
2）存储的效率NSArray要高一些
如果取值的时候是把所有的数据取出来，NSArray效率高
如果只是取数组中指定的几个元素，字典数组效率高

NSMutableDictionary：存储在其中的元素可以动态的新增和删除

创建可变字典数组：
1）有意义
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5ehtossj30an01kmy0.jpg)
2）
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5eorn5vj30bb017aao.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5ev5o60j309300vwep.jpg)

新增键值对：【如果键重复，后添加的就会替换原有的】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5f0tn78j30ba03r0tq.jpg)

删除所有键值对：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5f7h0phj30ba07atar.jpg)
删除某一个键值对：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5fdptw3j306j02a74k.jpg)

字典数组的信息持久化：保存到plist文件里：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5flzn7fj30bp044taj.jpg)
从plist文件中还原：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5fsa5waj30ff08qtbu.jpg)