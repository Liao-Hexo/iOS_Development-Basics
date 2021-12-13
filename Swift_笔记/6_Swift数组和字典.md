## Swift 数组

Swift 数组使用有序列表存储同一类型的多个值。相同的值可以多次出现在一个数组的不同位置中。

Swift 数组会强制检测元素的类型，如果类型不同则会报错，Swift 数组应该遵循像Array<Element>这样的形式，其中Element是这个数组中唯一允许存在的数据类型。

如果创建一个数组，并赋值给一个变量，则创建的集合就是可以修改的。这意味着在创建数组后，可以通过添加、删除、修改的方式改变数组里的项目。如果将一个数组赋值给常量，数组就不可更改，并且数组的大小和内容都不可以修改。

### 创建数组

```swift
import UIKit

//创建了一个类型为Int，数量为3，初始值为0的空数组
var someInts1 = [Int](repeating: 0, count: 3)

var someInts2: [Int] = []

//创建了含有三个元素的数组
var someInts3: [Int] = [10,20,30]
```

### 访问数组

我们可以根据数组的索引来访问数组的元素，index索引从0开始，即索引0对应第一个元素，索引1对应第二个元素

```swift
import UIKit

//创建了一个类型为Int，数量为3，初始值为10的空数组
var someInts = [Int](repeating: 10, count: 3)

print(someInts[0])
print(someInts[1])
print(someInts[2])
```

### 修改数组

你可以使用`append()`方法或者赋值运算符`+=`在数组末尾添加元素

![](https://tva1.sinaimg.cn/large/008i3skNly1gqx3wkbns0j30e60mmadb.jpg)

### 遍历数组

![](https://tva1.sinaimg.cn/large/008i3skNly1gqx44e7p52j30yh0u0wkx.jpg)

### 合并数组

可以使用加法操作符（+）来合并两种已存在的相同类型数组。新数组的数据类型会从两个数组的数据类型中推断出来

![image-20210527173142243](/Users/liaojialong/Library/Application Support/typora-user-images/image-20210527173142243.png)

### count属性

可以使用count属性来计算数组元素的个数

![](https://tva1.sinaimg.cn/large/008i3skNly1gqx4clhhxkj30ki0ecdhn.jpg)

### isEmpty属性

可以通过只读属性isEmpty来判断数组是否为空，返回布尔值

## Swift 字典

Swift 字典用来存储无序的相同类型数据的集合，Swift 字典会强制检测元素的类型，如果类型不同则会报错。

Swift 字典每个值（value）都关联唯一的键（key），键作为字典中的这个值数据的标识符。

和数组中的数据项不同，字典中的数据项并没有具体顺序。我们在需要通过标识符（键）访问数据的时候使用字典，这种方法很大程度上和我们在现实世界中使用字典查字义的方法一样。

Swift 字典的key没有类型限制可以是整型或字符串，但必须是唯一的。

如果创建一个字典，并赋值给一个变量，则创建的字典就是可以修改的。这意味着在创建字典后，可以通过添加、删除、修改的方式改变字典里的项目。如果将一个字典赋值给常量，字典就不可修改，并且字典的大小和内容都不可以修改

### 创建字典

```swift
import UIKit

//创建一个空字典，键的类型为Int，值的类型为String
var someDict1 = [Int: String]()

var someDict2: [Int: String] = [:]

var someDict3: [Int: String] = [1: "One", 2: "Two", 3: "Three"]
```

### 访问字典

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxw9bknbij60sm0fq0uz02.jpg)

### 修改字典

我们可以使用 **updateValue(forKey: )** 增加或更新字典的内容。如果 key 不存在，则添加值，如果存在则修改 key 对应的值。

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxwkuuzp3j30su0iugp2.jpg)

也可以通过指定的key来修改字典的值

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxwow9d71j30su0iuq6c.jpg)

### 移除Key-Value对

我们可以使用 **removeValueForKey()** 方法来移除字典 key-value 对。如果 key 存在该方法返回移除的值，如果不存在返回 nil 

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxwt4l01xj30su0fygoh.jpg)

也可以通过指定键的值为nil来移除key-value对

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxwvtn30nj30su0fygo5.jpg)

### 遍历字典

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxx2c8mjij30w60o4wjn.jpg)

### 字典转换为数组

可以提取字典的键值(key-value)对，并转换为独立的数组

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxx8uoz8dj30sq0lmtcj.jpg)

### count 属性

可以使用只读的count属性来计算字典有多少个键值对

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxxb8l0bmj30sq0eiq4g.jpg)

### isEmpty 属性

可以通过只读属性 **isEmpty** 来判断字典是否为空，返回布尔值

![](https://tva1.sinaimg.cn/large/008i3skNly1gqxxeuvzx5j30sq0eumzi.jpg)

