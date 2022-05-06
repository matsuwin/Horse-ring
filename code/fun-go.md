# Function

<br>

```go
package main

import "fmt"

// 匿名函数
var f1 = func() { fmt.Println("f1") }

// 命名函数
func f2() { fmt.Println("f2") }

// 不限长参数
func f3(a ...int) { fmt.Println("f3", a) }

// 任意类型参数
func f4(a interface{}) { fmt.Printf("f4 %T\n", a) }

// 多返回值
func f5() (n1, n2 int) {
    return 2, 3
}

func main() {

    // 延迟函数
    defer func() {
        fmt.Println("延迟函数")
    }()

    // 自执行函数
    func() {
        fmt.Println("自执行函数")
    }()

    f1()
    f2()
    f3(1, 2, 3, 4)
    f4("")
    n1, n2 := f5()
    fmt.Printf("f5 %d %d\n", n1, n2)
}
```
```
自执行函数
f1
f2
f3 [1 2 3 4]
f4 string
f5 2 3
延迟函数
```
