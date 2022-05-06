# Function

<br>

```kt
// 匿名函数
val f1 = fun() { println("f1") }

// 命名函数
fun f2() {
    println("f2")
}

// 不限长参数
fun f3(vararg a: Int) {
    println("f3 [${a.joinToString()}]")
}

// 任意类型参数
fun f4(a: Any) {
    println("f4 ${a::class.simpleName}")
}

fun main() {
    f1()
    f2()
    f3(1, 2, 3, 4)
    f4("")
}
```
```
f1
f2
f3 [1, 2, 3, 4]
f4 String
```
