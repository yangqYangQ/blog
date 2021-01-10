[上一级](../README.md)



# 学习 Swift

## 2.  MVVM 和 Swift 类型

Swift 中不同的类型包括：

`struct` 、`class` 、`functions` 、`generics 泛型` 、`protocol` 、`enum`

### 2.1 Generics

并不需要关心类型的类型

泛型的绝佳示例：`Array`

```swift
//声明 Array
//Element 是 类型参数（Type Parameter）
struct Array<Element> {
 . . .
 func append(_ element: Element) { . . . }
}

//使用 Array 时指定类型
var a = Array<Int>()
a.append(5)
a.append(22)
```



### 2.2 Functions

