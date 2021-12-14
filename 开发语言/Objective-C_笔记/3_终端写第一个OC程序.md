### OC程序的编译，链接，执行：

1. 在.m文件中写上符合OC语法规范的源代码：
clear清屏
cd /Users/ljlmacbookair/Desktop/OC2 
touch main.m

2. 使用编译器将源代码编译为目标文件【预处理，检查语法，编译】
cc -c main.m

3. 链接
![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3bloyncj30ft0550tb.jpg)
如果程序中使用到了框架中的函数或者类，那么在链接的时候，就必须要告诉编译器去哪一个框架中找这个函数或者类
cc main.o -framework Foundation

4. 链接成功以后就会生成一个a.out可执行文件，执行就可以了
./a.out

![](https://tva1.sinaimg.cn/large/0081Kckwly1gly3bty2jqj30i70apq3m.jpg)

- - - -

### OC程序和C程序各个阶段的后缀名：

    源文件   目标文件  可执行文件
C    .c       .o       .out
OC   .m       .o       .out