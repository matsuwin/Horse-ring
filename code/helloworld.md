# Hello World

<br>

***Clang***

```c
#include <stdio.h>

void main() {
    printf("Hello World\n");
}
```
```sh
# 普通编译
cc main.c -o main

# 静态编译
cc main.c -o main -static

# output 869K
```

<br>

***Cgo***

```go
package main

/*
#include <stdio.h>

void Main() {
    printf("Hello World\n");
}
*/
import "C"

func main() {
    C.Main()
}
```
```sh
# 普通编译
go build -o main main.go

# 静态编译
go build -o main -ldflags '-linkmode "external" -extldflags "-static"' main.go

# output 2.2M
```

<br>

***Kotlin***

```kt
fun main() {
    println("Hello World")
}
```
```sh
# 普通编译
kotlinc -d main.jar Main.kt

# 解释执行
java -jar main.jar

# output 1k
```

<br>

***Python***

```py
if __name__ == '__main__':
    print("Hello World")
```
```sh
# 解释执行
python main.py
```
