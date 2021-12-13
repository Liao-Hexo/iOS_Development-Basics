## Swift类

Swift类是构建代码所用的一种通用且灵活的构造体，我们可以为类定义属性(常量、变量)和方法，与其他编程语言所不同的是，Swift并不要求你为自定义类去创建独立的接口和实现文件，你所要做的是在一个单一文件中定义一个类，系统会自动生成面向其他代码的外部接口

### 类和结构体对比

共同点：

* 定义属性用于存储值
* 定义方法用于提供功能
* 定义附属脚本用于访问值
* 定义构造器用于生成初始化值
* 通过扩展以增加默认实现的功能
* 符合协议以对某类提供标准功能

类还具有的附加功能：

* 继承允许一个类继承另一个类的特征
* 类型转换允许在运行时检查和解释一个类实例的类型
* 解构器允许一个类实例释放任何其所被分配的资源
* 引用计数允许对一个类的多次引用

### 语法

```swift
import UIKit

class student {
    var studname: String = "John"
    var age: Int = 18
}

//实例化类
let studrecord = student()

//类的属性可以通过.来访问
print(studrecord.studname, studrecord.age)
```

### 恒等运算符

因为类是引用类型，有可能有多个常量和变量在后台同时引用某一个类实例，为了能够判定两个常量或者变量是否引用同一个类实例，Swift内建了两个恒等运算符

| **恒等运算符**                                  | **不恒等运算符**                                  |
| :---------------------------------------------- | :------------------------------------------------ |
| 运算符为：===                                   | 运算符为：!==                                     |
| 如果两个常量或者变量引用同一个类实例则返回 true | 如果两个常量或者变量引用不同一个类实例则返回 true |

![](https://tva1.sinaimg.cn/large/008i3skNly1gqz39bkyoxj60ia0ssn2j02.jpg)

## Swift属性

Swift属性将值跟特定的类、结构或枚举关联

属性可分为存储属性和计算属性：

| **存储属性**                   | **计算属性**             |
| :----------------------------- | :----------------------- |
| 存储常量或变量作为实例的一部分 | 计算（而不是存储）一个值 |
| 用于类和结构体                 | 用于类、结构体和枚举     |

### 存储属性

一个存储属性就是存储在特定类或结构体的实例里的一个常量或变量，存储属性可以是变量存储属性，也可以是常量存储属性

- 可以在定义存储属性的时候指定默认值
- 也可以在构造过程中设置或修改存储属性的值，甚至修改常量存储属性的值

```swift
import UIKit

struct Number {
    var digits: Int
    let Pi = 3.1415  //代码中Pi在定义存储属性的时候指定默认值，所以不管你什么时候实例化结构体，它都不会改变
    //如果你定义的是一个常量存储属性，如果尝试修改它就会报错
}

var n = Number(digits: 12345)
n.digits = 12

print(n.digits, n.Pi)
```

### 延迟存储属性

延迟存储属性是指当第一次被调用的时候才会计算其初始值的属性，在属性声明前使用`lazy`来标示一个延迟存储属性

注意：必须将延迟存储属性声明成变量，因为属性的值在实例构造完成之前可能无法得到，，而常量属性在构造过程完成之前必须要有初始值，因此无法声明成延迟属性

延迟存储属性一般用于：延迟对象的创建、当属性的值依赖于其他未知类

```swift
import UIKit

class sample {
    lazy var no = number()
}

class number {
    var name = "Swift"
}

var firstsample = sample()
print(firstsample.no.name)
```

### 计算属性

除存储属性外，类、结构体和枚举可以定义计算属性，计算属性不直接存储值，而是提供一个getter来获取值，一个可选的setter来间接设置其他属性或变量的值

![image-20210529110941684](/Users/liaojialong/Library/Application Support/typora-user-images/image-20210529110941684.png)

### 只读计算属性

只有getter没有setter的计算属性就是只读计算属性，只读计算属性总是返回一个值，可以通过`.`运算符访问，但不能设置新的值

![image-20210529111909855](/Users/liaojialong/Library/Application Support/typora-user-images/image-20210529111909855.png)

### 属性观察器

属性观察器监控和响应属性值的变化，每次属性被设置值的时候都会调用属性观察器，甚至新的值和现在的值相同的时候也不例外。可以为除了延迟存储属性之外的其他存储属性添加属性观察器，也可以通过重载属性的方式为继承的属性（包括存储属性和计算属性）添加属性观察器。

注意：不需要为无法重载的计算属性添加属性观察器，因为可以通过 setter 直接监控和响应值的变化。

可以为属性添加如下的一个或全部观察器：

* `willSet`在设置新的值之前调用
* `didSet`在新的值被设置之后立即调用
* willSet和didSet观察器在属性初始化过程中不会被调用

![](https://tva1.sinaimg.cn/large/008i3skNly1gqz4yplmdmj30p40rcn1z.jpg)

### 全局变量和局部变量

计算属性和属性观察器所描述的模式也可以用于全局变量和局部变量

| **局部变量**                       | **全局变量**                               |
| :--------------------------------- | :----------------------------------------- |
| 在函数、方法或闭包内部定义的变量。 | 函数、方法、闭包或任何类型之外定义的变量。 |
| 用于存储和检索值。                 | 用于存储和检索值。                         |
| 存储属性用于获取和设置值。         | 存储属性用于获取和设置值。                 |
| 也用于计算属性。                   | 也用于计算属性。                           |

### 类型属性

属性可以直接用于类型本身，这种属性称为类型属性

类型属性是作为类型定义的一部分写在类型最外层的花括号`{}`内。

使用关键字 static 来定义值类型的类型属性，关键字 class 来为类定义类型属性。

```swift
struct Structname {
   static var storedTypeProperty = " "
   static var computedTypeProperty: Int {
      // 这里返回一个 Int 值
   }
}

enum Enumname {
   static var storedTypeProperty = " "
   static var computedTypeProperty: Int {
      // 这里返回一个 Int 值
   }
}

class Classname {
   class var computedTypeProperty: Int {
      // 这里返回一个 Int 值
   }
}

//注意：例子中的计算型类型属性是只读的，但也可以定义可读可写的计算型类型属性，跟实例计算属性的语法类似。
```

### 获取和设置类型属性的值

类似于实例的属性，类型属性的访问也是通过点运算符(.)来进行。但是，类型属性是通过类型本身来获取和设置，而不是通过实例。

```swift
import UIKit

struct StudMarks {
    
   static let markCount = 97
   static var totalCount = 0
    
   var InternalMarks: Int = 0 {
      didSet {
         if InternalMarks > StudMarks.markCount {
            InternalMarks = StudMarks.markCount
         }
         if InternalMarks > StudMarks.totalCount {
            StudMarks.totalCount = InternalMarks
         }
      }
   }
}

var stud1Mark1 = StudMarks()
var stud1Mark2 = StudMarks()

stud1Mark1.InternalMarks = 98
print(stud1Mark1.InternalMarks)  //97
print(StudMarks.markCount)  //97
print(StudMarks.totalCount)  //97

stud1Mark2.InternalMarks = 87
print(stud1Mark2.InternalMarks)  //87
print(StudMarks.markCount)  //97❓
print(StudMarks.totalCount)  //97❓
```

## Swift方法

