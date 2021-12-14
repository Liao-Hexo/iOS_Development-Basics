## Swift介绍

Swift是一种支持多编程范式和编译式的开源编程语言，苹果于2014年WWDC发布

Swift结合了C和Objective-C的优点并且不受C兼容性的限制

2015年6月8日，苹果于WWDC 2015上宣布，Swift将开放源代码，包括编译器和标准库

## Playground

Swift的playground就像是一个可交互的文档，它是用来练手学Swift的，写一句代码出一行结果，可以实时查看代码的结果，是学习Swift语言的利器

playground创建iOS程序默认代码如下：

```swift
import UIKit

var greeting = "Hello, playground"
```

创建macOS程序默认代码：

```swift
import Cocoa

var greeting = "Hello, playground"
```

## Swift基本语法

### Swift引入

我们可以使用 **import** 语句来引入任何的 Objective-C 框架（或 C 库）到 Swift 程序中。例如 **import cocoa** 语句导入了使用了 Cocoa 库和API，我们可以在 Swift 程序中使用他们。Cocoa 本身由 Objective-C 语言写成，Objective-C 又是 C 语言的严格超集，所以在 Swift 应用中我们可以很简单的混入 C 语言代码，甚至是 C++ 代码。

### Swift标记

Swift程序由多种标记组成，标记可以是单词、标识符、常量、字符串或符号

`print("test")`

### Swift注释

Swift的注释与C语言极其相似，单行注释以两个反斜杠开头

多行注释以`/*`开始，以`*/`结束

与C语言的多行注释有所不同的是，Swift的多行注释可以嵌套在其他多行注释内部，多行注释的嵌套使你可以更快捷方便的注释代码块，即使代码块中已经有了注释

```swift
//这是一行注释

/* 这也是一条注释
 但跨越多行 */

/* 这是第一个多行注释的开头
 
 /* 这是嵌套的第二个多行注释 */
 
 这是第一个多行注释的结尾 */
```

### 分号

与其他语言不同的是，Swift不要求在每行语句的结尾使用分号(;)，但当你在同一行书写多条语句时，必须用分号隔开

```swift
import UIKit

var greeting = "Hello, playground"; print(greeting)
```

### 标识符

标识符就是给变量、常量、方法、函数、枚举、结构体、类、协议等指定的名字

- Swift语言中标识符的命名规则：
  1. 区分大小写
  2. 标识符首字符可以以下划线(_)或者字母开始，但不能是数字
  3. 标识符中其他字符可以是下划线、字母或数字

如果一定要使用关键字作为标识符，可以在关键字前后添加重音符号(`)

```swift
let `class` = "Runoob"
```

### 关键字

关键字是类似于标识符的保留字符序列，除非用重音符号将其括起来，否则不能用作标识符，关键字是对编译器具有特殊意义的预定义保留标识符

#### 与声明有关的关键字

| class     | deinit   | enum    | extension |
| --------- | -------- | ------- | --------- |
| func      | import   | init    | internal  |
| let       | operator | private | protocol  |
| public    | static   | struct  | subscript |
| typealias | var      |         |           |

#### 与语句有关的关键字

| break | case  | continue    | default |
| ----- | ----- | ----------- | ------- |
| do    | else  | fallthrough | for     |
| if    | in    | return      | switch  |
| where | while |             |         |

#### 表达式和类型关键字

| as       | dynamicType | false    | is           |
| -------- | ----------- | -------- | ------------ |
| nil      | self        | Self     | super        |
| true     | `_COLUMN_`  | `_FILE_` | `_FUNCTION_` |
| `_LINE_` |             |          |              |

#### 在特定上下文中使用的关键字

| associativity | convenience | dynamic  | didSet   |
| ------------- | ----------- | -------- | -------- |
| final         | get         | infix    | inout    |
| lazy          | left        | mutating | none     |
| nonmutating   | optional    | override | postfix  |
| precedence    | prefix      | Protocol | required |
| right         | set         | Type     | unowned  |
| weak          | willSet     |          |          |

### Swift空格

Swift语言并不是像C/C++、Java那样完全忽视空格，Swift对空格的使用有一定的要求，但是又不像Python对缩进的要求那么严格

在Swift中，运算符不能直接跟在变量或常量的后面

```swift
//推荐使用这种写法
let a = 1 + 2
```

### Swift字面量

所谓字面量，就是指像特定的数字、字符串或者是布尔值这样，能够直接了当的指出自己的类型并为变量进行赋值的值

```swift
42                 // 整型字面量
3.14159            // 浮点型字面量
"Hello, world!"    // 字符串型字面量
true               // 布尔型字面量
```

### 打印输出

```swift
print("Runoob")  //输出Runoob
```

如果我们想让其不换行输出，只需要将最后一个参数赋值为空字符串即可：

```swift
for x in 0...10 {
    print("\(x) ", terminator: "")
}

for x in 0...10 {
    print("\(x) ")
}
```

如果你需要接收用户的输入可以使用 **readLine()**

```swift
let theInput = readLine()
```