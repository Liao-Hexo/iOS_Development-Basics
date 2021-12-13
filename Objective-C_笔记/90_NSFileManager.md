NSFileManager是Foundation框架提供的一个类，用来操作磁盘上的文件和文件夹，对它们进行创建、删除、复制、拷贝、移动

NSFileManager类的对象是以单例模式创建的：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5hp8zrzj30a801h0t2.jpg)

常用方法之判断：
1）判断指定的文件或者文件夹在磁盘上是否真实的存在
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5hwrwlrj30ao084tb6.jpg)
2）判断指定的路径是否真实的存储在我们的磁盘之上，并且判断这个路径是一个文件夹路径还是一个文件路径
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5i34wtlj30b30at41h.jpg)
3）判断指定的文件夹或者文件是否可以读取
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5iam1klj30e503nq4e.jpg)
4）判断指定的文件夹或者文件是否可以写入
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5ih8vqpj30ce01vjs5.jpg)
5）判断指定的文件夹或者文件是否可以删除
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5imyiflj30al01vmxv.jpg)

常用方法之获取信息：
1）获取指定文件或者文件夹的属性信息
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5iurvuij30ig09j0wu.jpg)
只是想拿到文件或文件夹的大小信息：
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5j2k4vtj30hp02h75e.jpg)
2）获取指定目录下的所有的文件和目录【所有的都拿到】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5j9tj1qj30e5031wfo.jpg)
3）获取指定目录下所有的子目录和文件【不包括孙子辈】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5jghamuj30hn055770.jpg)

常用方法之文件/目录的创建：
1）在指定的目录创建文件
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5jn99twj30hu0avwht.jpg)
2）在指定的目录创建文件夹【第2个参数：YES做一路创建，NO就不会】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5jvbsdpj30hs04xmyp.jpg)
3）拷贝文件
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5k3djl0j30if04emz8.jpg)
4）移动/剪切文件—文件的重命名
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5kdngvaj30i0028t9s.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5kja7xfj30i0028dh1.jpg)
5）删除文件【删除的文件不会倒在废纸篓，而是直接删除】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5kpuzkyj30f4028gmj.jpg)

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly5kx5ehjj30dx0b0wi3.jpg)