1）block是一个数据类型，我们可以声明一个block类型的变量
2）不同类型的变量中可以存储不同类型的数据，block类型的变量中专门存储一段代码，这段代码可以有参数，可以有返回值


Block变量的声明：
1）虽然block变量中是用来存储一段代码的，但是一个block变量中并不是任意的一段代码都可以存进去的，而是有限定的；也就是说，声明block变量的时候，必须要指定这个block变量存储的代码是否有参数，是否有返回值，一旦指定以后，这个block变量中就只能存储这样的代码段了
2）语法：返回值类型 (^block变量的名称)(参数列表);
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4hpakdcj30fg02j3zi.jpg)

初始化block变量：
1）原理：写一个符合block要求的代码段，存储到block变量中就可以了
2）代码段的书写格式：

              ^返回值类型(参数类型){
                        代码段;
              };
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4i0b989j303y02i0t6.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4i7bl9oj305j01vglz.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4idsc7nj305j01v74m.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4ikffggj30b901vdgd.jpg)
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly4iq8m2dj30e209wt9y.jpg)

  如何执行存储在block变量中的代码段：
语法格式：block变量名();
【有参数就传参数，有返回值就接】