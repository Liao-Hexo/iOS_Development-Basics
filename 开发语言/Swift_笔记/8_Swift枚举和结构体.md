## Swift 枚举

枚举简单的说也是一种数据类型，只不过是这种数据类型只包含自定义的特定数据，它是一组有共同特性的数据的集合

枚举的功能为：

* 它声明在类中，可以通过实例化类来访问它的值。
* 枚举也可以定义构造函数（initializers）来提供一个初始成员值；可以在原始的实现基础上扩展它们的功能。
* 可以遵守协议（protocols）来提供标准的功能。

### 语法

```swift
import UIKit

//定义枚举
enum DaysofaWeek {
    case Sunday  //case关键词表示一行新的成员值将被定义
    case Monday
    case TUESDAY
    case WEDNESDAY
    case THURSDAY
    case FRIDAY
    case Saturday
}

var weekDay = DaysofaWeek.THURSDAY

switch weekDay {
  
case .Sunday:
    print("星期天")
case .Monday:
    print("星期一")
case .TUESDAY:
    print("星期二")
case .WEDNESDAY:
    print("星期三")
case .THURSDAY:
    print("星期四")
case .FRIDAY:
    print("星期五")
case .Saturday:
    print("星期六")
}
```

注意：和 C 和 Objective-C 不同，Swift 的枚举成员在被创建时不会被赋予一个默认的整型值。在上面的*`DaysofaWeek`*例子中，*`Sunday`*，*`Monday`*，*`……`*和*`Saturday`*不会隐式地赋值为*`0`*，*`1`*，*`……`*和*`6`*。相反，这些枚举成员本身就有完备的值，这些值是已经明确定义好的*`DaysofaWeek`*类型。

枚举可分为相关值与原始值：

| 相关值                                                       | 原始值                |
| :----------------------------------------------------------- | :-------------------- |
| 不同数据类型                                                 | 相同数据类型          |
| 实例: enum {10,0.8,"Hello"}                                  | 实例: enum {10,35,50} |
| 值的创建基于常量或变量                                       | 预先填充的值          |
| 相关值是当你在创建一个基于枚举成员的新常量或变量时才会被设置，并且每次当你这么做得时候，它的值可以是不同的。 | 原始值始终是相同的    |

### 相关值

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy7zaz6thj319u0n4wkk.jpg)

### 原始值

原始值可以是字符串，字符，或者任何整型值或浮点型值。每个原始值在它的枚举声明中必须是唯一的。

在原始值为整数的枚举时，不需要显式的为每一个成员赋值，Swift会自动为你赋值。例如，当使用整数作为原始值时，隐式赋值的值依次递增1。如果第一个值没有被赋初值，将会被自动置为0。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy83cuaq2j30ia0n4tbw.jpg)

## Swift 结构体

Swift 结构体是构建代码所用的一种通用且灵活的构造体。我们可以为结构体定义属性（常量、变量）和添加方法，从而扩展结构体的功能。

与 C 和 Objective C 不同的是：

* 结构体不需要包含实现文件和接口。 
* 结构体允许我们创建一个单一文件，且系统会自动生成面向其它代码的外部接口。 

结构体总是通过被复制的方式在代码中传递，因此它的值是不可修改的。

```swift
import UIKit

struct MarkStruct {
    var mark1: Int = 100
    var mark2: Int = 78
    var mark3: Int = 98
}

//结构体实例化
var marks = MarkStruct()

print(marks.mark1, marks.mark2, marks.mark3)
```

### 结构体应用

在代码中，你可以使用结构体来定义你的自定义数据类型，结构体实例总是通过值传递来定义你的自定义数据类型

```swift
import UIKit

struct ReSolution {
    var width = 0
    var height = 0
}

// 创建一个结构体
let hd = ReSolution(width: 1920, height: 1080)

// 结构体赋值,实际上做的是拷贝操作,cinema和hd结构体在内存中各自占用独立的空间
var cinema = hd

// 修改cinema结构体,不会影响hd结构体
cinema.width = 2048

print("cinema is now \(cinema.width) pixels wide") // return:2048
print("hd is still \(hd.width) pixels wide")       // return:1920
```

与值类型不同，引用类型在被赋予到一个变量、常量或者被传递到一个函数时，操作的并不是其拷贝。因此，引用的是已存在的实例本身而不是其拷贝。类就是引用类型。

```swift
import UIKit

class ResolutionClass {
    var width = 0
    var height = 0
    
    init(width: Int,height: Int) {
        self.width = width
        self.height = height
    }
}

// 创建一个类对象
let hdClass = ResolutionClass(width: 1920, height: 1080)

// 类对象赋值,引用同一个内存空间
var cinemaClass = hdClass

// 修改cinema对象,本质上也是修改hdClass对象
cinemaClass.width = 2048

print("cinemaClass is now \(cinemaClass.width) pixels wide")  // return: 2048
print("hdClass is also \(hdClass.width) pixels wide")         // return: 2048
```

