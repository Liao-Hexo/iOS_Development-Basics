
1）如果我们写的代码段没有返回值，那么代码段的void可以省略【既没有参数也没有返回值，代码段的void和小括弧都省略，只写一个^】
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4jb918tj305501vwes.jpg)
注意：这里说的是代码段的返回值如果是void可以省略，声明block变量的返回值无论是什么都不可以省略
2）如果我们写的代码段没有参数，那么代码段的小括弧可以省略
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4jj02nbj305501vaad.jpg)
3）声明block变量的时候，如果有指定参数，可以只写参数的类型而不写参数的名称
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4jpbdmzj309k01vaal.jpg)
注意：这个地方我们说的是声明block变量的时候，代码段的类型和名称都要写
4）无论代码段是否有返回值，在写代码的时候，可以不写返回值类型，省略；如果在写代码段的时候，省略了返回值，这个时候系统会自动的确定返回值的类型，如果代码段中没有返回任何数据，那么它会认为这个代码段是没有返回值的，如果代码段中有返回数据，返回的数据是什么类型它就会认为这个代码段是什么类型
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4jviexhj309k01v0t6.jpg)


建议：仍然按照我们最标准的写法来写block变量和block代码段，因为这样可以提高代码的阅读性