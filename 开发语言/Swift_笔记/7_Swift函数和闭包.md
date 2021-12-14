## Swift函数

Swift函数用来完成特定任务的独立的代码块

- 函数声明：告诉编译器函数的名字、返回类型及参数
- 函数定义：提供了函数的实体

### 函数定义和调用

Swift 定义函数使用关键字 **func**。

定义函数的时候，可以指定一个或多个输入参数和一个返回值类型。

每个函数都有一个函数名来描述它的功能。通过函数名以及对应类型的参数值来调用这个函数。函数的参数传递的顺序必须与参数列表相同。

函数的实参传递的顺序必须与形参列表相同，**->** 后定义函数的返回值类型。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxydhh9ldj30jo0e60ud.jpg)

### 函数参数

函数可以接受一个或者多个参数，这些参数被包含在函数的括号中，以逗号分隔

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxyjowc6rj30qg0e676g.jpg)

### 不带参数的函数

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxyp7yv8xj30dg0e6jsi.jpg)

### 元组作为函数的返回值

函数返回值类型可以是字符串，整型，浮点型等。

元组与数组类似，不同的是，元组中的元素可以是任意类型，使用的是圆括号。

你可以用元组（tuple）类型让多个值作为一个复合值从函数中返回。

```swift
import UIKit

//在一个Int数组中找出最小值和最大值
func minMax(array: [Int]) -> (min: Int, max: Int) {
    
    var currentMin = array[0]
    var currentMax = array[0]
    
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}

let bounds = minMax(array: [8, -6, 2, 109, 3, 71])
print("最小值为 \(bounds.min) ，最大值为 \(bounds.max)")
```

```swift
import UIKit

//如果你不确定返回的元组一定不为nil，那么你可以返回一个可选的元组类型
//注意：可选元组类型如(Int, Int)?与元组包含可选类型如(Int?, Int?)是不同的.可选的元组类型，整个元组是可选的，而不只是元组中的每个元素值。

//前面的minMax(_:)函数返回了一个包含两个Int值的元组。但是函数不会对传入的数组执行任何安全检查，如果array参数是一个空数组，如上定义的minMax(_:)在试图访问array[0]时会触发一个运行时错误。为了安全地处理这个"空数组"问题，将minMax(_:)函数改写为使用可选元组返回类型，并且当数组为空时返回nil
func minMax(array: [Int]) -> (min: Int, max: Int)? {
    
    if array.isEmpty {
        return nil
    }
    
    var currentMin = array[0]
    var currentMax = array[0]
    
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}

let bounds = minMax(array: [8, -6, 2, 109, 3, 71])
print("最小值为 \(bounds!.min) ，最大值为 \(bounds!.max)")
```

### 没有返回值的函数

```swift
import UIKit

func runoob(site: String) {
    print("菜鸟教程官网： \(site)")
}

runoob(site: "http://www.runoob.com")
```

### 函数参数名称

函数参数都有一个外部参数名和一个局部参数名

#### 局部参数名在函数的实现内部使用

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxzjw8f1rj30i80gejtj.jpg)

#### 外部参数名

可以在局部参数名前指定外部参数名，中间以空格分隔，外部参数名用于在函数调用时传递给函数的参数。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxzrhryerj30pe0h6goc.jpg)

### 可变参数

可变参数可以接受零个或多个值。函数调用时，你可以用可变参数来指定函数参数，其数量是不确定的。可变参数通过在变量类型名后面加入（...）的方式来定义。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxzyhr9mbj30l60kw0vy.jpg)

### 常量、变量、I/O参数

一般默认在函数中定义的参数都是常量参数，也就是这个参数你只可以查询使用，不能改变它的值。如果想要声明一个变量参数，可以在参数定义前加 inout 关键字，这样就可以改变这个参数的值了。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy07v0ljfj31as0kgdku.jpg)

### 函数类型及使用

每个函数都有种特定的函数类型，由函数的参数类型和返回类型组成

#### 使用函数类型

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy0g0p7ayj30z60feadc.jpg)

### 函数类型作为参数类型，函数类型作为返回类型

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy0nlakyxj30rw0j8n12.jpg)

### 函数嵌套

函数嵌套指的是函数内定义一个新的函数，外部的函数可以调用函数内定义的函数。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy2qj7asoj30ra0kgwhx.jpg)

## Swift闭包

闭包是自包含的功能代码块，可以在代码中使用或者用来作为参数传值，全局函数和嵌套函数其实就是特殊的闭包

闭包的形式：

| 全局函数                 | 嵌套函数                         | 闭包表达式                                           |
| ------------------------ | -------------------------------- | ---------------------------------------------------- |
| 有名字但不能捕获任何值。 | 有名字，也能捕获封闭函数内的值。 | 无名闭包，使用轻量级语法，可以根据上下文环境捕获值。 |

Swift中的闭包有很多优化的地方: 

1. 根据上下文推断参数和返回值类型
2. 从单行表达式闭包中隐式返回（也就是闭包体只有一行代码，可以省略return）
3. 可以使用简化参数名，如$0, $1(从0开始，表示第i个参数...)
4. 提供了尾随闭包语法(Trailing closure syntax)

### 语法

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy3c1w56bj30ik0k8771.jpg)

### 闭包表达式

闭包表达式是一种利用简洁语法构建内联闭包的方式，闭包表达式提供了一些语法优化，使得撰写闭包变的简单明了

#### sorted 方法

1. Swift 标准库提供了名为 **sorted(by:)** 的方法，会根据您提供的用于排序的闭包函数将已知类型数组中的值进行排序。 排序完成后，sorted(by:) 方法会返回一个与原数组大小相同，包含同类型元素且元素已正确排序的新数组。原数组不会被 sorted(by:) 方法修改。

2. sorted(by:)方法需要传入两个参数：

3. * 已知类型的数组
   * 闭包函数，该闭包函数需要传入与数组元素类型相同的两个值，并返回一个布尔类型值来表明当排序结束后传入的第一个参数排在第二个参数前面还是后面。如果第一个参数值出现在第二个参数值前面，排序闭包函数需要返回 **true**，反之返回 **false**。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy3n6bhjij31na0hqjxq.jpg)

### 参数名称缩写

Swift自动为内联函数提供了参数名称缩写功能，可以直接通过`$0,$1,$2`来顺序调用闭包的参数

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy3v0zd98j30lg0eg0uv.jpg)

### 运算符函数

Swift 的`String`类型定义了关于大于号 (`>`) 的字符串实现，其作为一个函数接受两个`String`类型的参数并返回`Bool`类型的值。 而这正好与`sort(_:)`方法的第二个参数需要的函数类型相符合。 因此，可以简单地传递一个大于号，Swift可以自动推断出您想使用大于号的字符串函数实现

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy3yike4nj30lg0egwg7.jpg)

### 尾随闭包

尾随闭包是一个书写在函数括号之后的闭包表达式，函数支持将其作为最后一个参数调用

![](https://tva1.sinaimg.cn/large/008i3skNly1gqy43w5sm0j30lg0eg0um.jpg)

### 捕获值

1. 闭包可以在其定义的上下文中捕获常量或变量。

2. 即使定义这些常量和变量的原域已经不存在，闭包仍然可以在闭包函数体内引用和修改这些值。

3. Swift最简单的闭包形式是嵌套函数，也就是定义在其他函数的函数体内的函数。 

4. 嵌套函数可以捕获其外部函数所有的参数以及定义的常量和变量。

```swift
import UIKit

func makeIncrementor(forIncrement amount: Int) -> () -> Int {
    
    var runningTotal = 0
    
    //incrementor函数并没有获取任何参数，但是在函数体内访问了runningTotal和amount变量。这是因为其通过捕获在包含它的函数体内已经存在的runningTotal和amount变量而实现。由于没有修改amount变量，incrementor实际上捕获并存储了该变量的一个副本，而该副本随着incrementor一同被存储。所以我们调用这个函数时会累加
    func incrementor() -> Int {
        runningTotal += amount
        return runningTotal
    }
    
    return incrementor
}

let incrementByTen = makeIncrementor(forIncrement: 10)

print(incrementByTen())  //返回值为10

print(incrementByTen())  //返回值为20

print(incrementByTen())  //返回值为30
```

### 闭包是引用类型

1. 上面的例子中，incrementByTen是常量，但是这些常量指向的闭包仍然可以增加其捕获的变量值。这是因为函数和闭包都是引用类型。

2. 无论您将函数/闭包赋值给一个常量还是变量，您实际上都是将常量/变量的值设置为对应函数/闭包的引用。 上面的例子中，incrementByTen指向闭包的引用是一个常量，而并非闭包内容本身。这也意味着如果您将闭包赋值给了两个不同的常量/变量，两个值都会指向同一个闭包

```swift
import UIKit

func makeIncrementor(forIncrement amount: Int) -> () -> Int {
    
    var runningTotal = 0
    
    //incrementor函数并没有获取任何参数，但是在函数体内访问了runningTotal和amount变量。这是因为其通过捕获在包含它的函数体内已经存在的runningTotal和amount变量而实现。由于没有修改amount变量，incrementor实际上捕获并存储了该变量的一个副本，而该副本随着incrementor一同被存储。所以我们调用这个函数时会累加
    func incrementor() -> Int {
        runningTotal += amount
        return runningTotal
    }
    
    return incrementor
}

let incrementByTen = makeIncrementor(forIncrement: 10)

print(incrementByTen())  //返回值为10

print(incrementByTen())  //返回值为20

print(incrementByTen())  //返回值为30

let alsoIncrementByTen = incrementByTen
print(alsoIncrementByTen())  //返回值也为40

//这里的值没有发生改变，是因为函数被调用结束就被释放了，没有用一个常量或变量去引用它，相当于每次调用都是一个新的函数
print(makeIncrementor(forIncrement: 20)())  //结果为20
print(makeIncrementor(forIncrement: 20)())  //结果为20
print(makeIncrementor(forIncrement: 20)())  //结果为20
```

