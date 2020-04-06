##  Kotlin问题汇总
- #### 带接收者的函数字面值
Kotlin 提供了使用指定的 接收者对象 调用函数字面值的功能。在函数字面值的函数体中，可以调用该接收者对象上的方法而无需任何额外的限定符。这类似于扩展函数，它允许你在函数体内访问接收者对象的成员。其用法的最重要的示例之一是类型安全的 [Groovy-风格构建器](https://www.jianshu.com/p/d74c6b86af5c)。
```
class HTML {
    fun body() { …… }
}
fun html(init: HTML.() -> Unit): HTML {
    val html = HTML()  // 创建接收者对象
    html.init()        // 将该接收者对象传给该 lambda
    return html
}
html {       // 带接收者的 lambda 由此开始
    body()   // 调用该接收者对象的一个方法
}
```
