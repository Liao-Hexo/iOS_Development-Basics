## Swift 字符串

Swift字符串是一系列字符的集合，它的数据类型为String

### 创建字符串

可以通过使用字符串字面量或String类的实例来创建一个字符串

```swift
import UIKit

//使用字符串字面量
var stringA = "Hello,World!"
print(stringA)

//String实例化
var stringB = String("Hello,World!")
print(stringB)
```

### 空字符串

可以使用字符串属性isEmpty来判断字符串是否为空

![](https://tva1.sinaimg.cn/large/008i3skNly1gqx0hlqt4rj30fs0l6djg.jpg)

### 字符串常量

可以将一个字符串赋值给一个变量或常量，变量是可修改的，常量是不可修改的

```swift
import UIKit

//变量是可修改的，常量是不可修改的
var stringA = "hello "
stringA += "world"
print(stringA)
```

### 字符串中插入值

字符串插值是一种构建新字符串的方式，可以在其中包含常量、变量、字面量和表达式。插入的字符串字面量的每一项都在以反斜线为前缀的圆括号中

```swift
import UIKit

var varA = 20
let constA = 100
var varC: Float = 20.0

var stringA = "\(varA) 乘以 \(constA) 等于 \(varC * 100)"
print(stringA)
```

### 字符串连接

字符串可以通过`+`连接

```swift
let constA = "hello "
let constB = "world"

var stringA = constA + constB
print(stringA)
```

### 字符串长度

```swift
import UIKit

var varA = "www.baidu.com"
print("\(varA), 长度为\(varA.count)")
```

### 字符串比较

可以使用`==`来比较两个字符串是否相等

### Unicode字符串

Unicode 是一个国际标准，用于文本的编码，Swift 的 String 类型是基于 Unicode建立的。你可以循环迭代出字符串中 UTF-8 与 UTF-16 的编码

![](https://tva1.sinaimg.cn/large/008i3skNly1gqx15s0bvmj30ho1120yl.jpg)

### 字符串函数及运算符

| 序号 | 函数/运算符 & 描述                                           |
| :--- | :----------------------------------------------------------- |
| 1    | **isEmpty**  判断字符串是否为空，返回布尔值                  |
| 2    | **hasPrefix(prefix: String)**  检查字符串是否拥有特定前缀    |
| 3    | **hasSuffix(suffix: String)**  检查字符串是否拥有特定后缀    |
| 4    | **Int(String)**  转换字符串数字为整型。 实例: `let myString: String = "256" let myInt: Int? = Int(myString)` |
| 5    | **String.count**  计算字符串的长度                           |
| 6    | **utf8**  您可以通过遍历 String 的 utf8 属性来访问它的 UTF-8 编码 |
| 7    | **utf16**  您可以通过遍历 String 的 utf8 属性来访问它的 utf16 编码 |
| 8    | **unicodeScalars**  您可以通过遍历String值的unicodeScalars属性来访问它的 Unicode 标量编码 |
| 9    | **+**  连接两个字符串，并返回一个新的字符串                  |
| 10   | **+=**  连接操作符两边的字符串并将新字符串赋值给左边的操作符变量 |
| 11   | **==**  判断两个字符串是否相等                               |
| 12   | **<**  比较两个字符串，对两个字符串的字母逐一比较            |
| 13   | **!=**  比较两个字符串是否不相等                             |

## Swift 字符(Character)

Swift的字符是一个单一的字符串字面量，数据类型为Character

```swift
import UIKit

//如果你想在Character类型的常量中存储更多的字符，则程序执行会报错
let char1: Character = "A"
let char2: Character = "B"

print(char1)
print(char2)
```

### 空字符变量

Swift中不能创建空的Character类型变量或常量

### 遍历字符串中的字符

Swift 的 String 类型表示特定序列的 Character（字符） 类型值的集合。 每一个字符值代表一个 Unicode 字符

```swift
import UIKit

for ch in "baidu" {
    print(ch)
}
```

### 字符串连接字符

```swift
import UIKit

var varA: String = "Hello "
let varB: Character = "G"

varA.append(varB)

print(varA)
```

