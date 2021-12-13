## Swift条件语句

条件语句通过设定一个或多个条件来执行程序，在条件为真时执行指定的语句，在条件为false时执行另外指定的语句

1. if、if let、guard let
5. switch 语句
6. 三目：a ? b : c

```swift
//C语言中有一个非零即真，Swift中只有true/false
import UIKit

let oName: String? = "john"
let oAge: Int? = 20

if oName != nil && oAge != nil {
    print("\(oName!), \(oAge!)")
}

//if let 可以设置数值，进入分支后，name、age可以保证一定有值
//if let 语句中不能使用&& ||条件
if let name = oName, let age = oAge {
    print("\(name), \(age)")
}
```

```swift
import UIKit

let oName: String? = "john"
let oAge: Int? = 20

func demo() {
    
    //guard是和if let刚好相反的指令
    guard let name = oName, let age = oAge else {
        return
    }

    //代码执行到此，name和age一定有值
    print("\(name), \(age)")
}

demo()
```

![](https://tva1.sinaimg.cn/large/008i3skNly1gsr05it9clj30d20rdjsh.jpg)

## Swift循环语句

有的时候，我们可能需要多次执行同一块代码。一般情况下，语句是按顺序执行的：函数中的第一个语句先执行，接着是第二个语句，依此类推。编程语言提供了更为复杂执行路径的多种控制结构。循环语句允许我们多次执行一个语句或语句组

### 循环类型

1. for in
2. for 循环：该循环方式在Swift3中已经弃用
3. while 循环
4. repeat while 循环：类似 while 语句，区别在于判断循环条件之前，先执行一次循环的代码块

### 循环控制语句

循环控制语句改变你代码的执行顺序，通过它你可以实现代码的跳转

| 控制语句                                                     | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [continue 语句](https://www.runoob.com/swift/swift-continue-statement.html) | 告诉一个循环体立刻停止本次循环迭代，重新开始下次循环迭代。   |
| [break 语句](https://www.runoob.com/swift/swift-break-statement.html) | 中断当前循环。                                               |
| [fallthrough 语句](https://www.runoob.com/swift/swift-fallthrough-statement.html) | 如果在一个case执行完后，继续执行下面的case，需要使用fallthrough(贯穿)关键字。 |