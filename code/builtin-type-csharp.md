# Built-in type for Csharp

<br>

```go
// Demo code

var num int32
fmt.Printf("%T:%d\n", num, num)

// int32:0
```

<br>

## *Value type*
*值类型的变量直接存储值，参数传递时，传递的是一个副本*

```cs
// bool 布尔类型，可以是两种状态 true 和 false
bool has = false

// int 有符号整数类型
int8:sbyte, int16:short, int32:int, int64:lang

// uint 无符号整数类型
uint8:byte, uint16:ushort, uint32:uint, uint64:ulang

// float32 浮点数类型
float32:float, float64:double

// string 字符串类型，8位字节序列。默认使用 UTF-8 文本编码，值不可变
string str = "";

// array 数组类型

// uintptr 指针整数类型，可以存储任何指针
```

<br>

## *Reference type*
*引用类型的变量存储的是一个地址，参数传递时，传递的是变量本身*

```go
// error 错误类型，内置的错误类型接口
type error interface {
	Error() string
}

// pointer 指针类型，可以指向任意类型的指针，在 unsafe 包中定义
var pointer unsafe.Pointer

// slice
var slice = make([]int, len, cap)

// map
var sets = make(map[int]int, cap)

// channel
var channel = make(chan int, cap)

// function
var function = func() {}
```

<br>

## *Empty type*
*空类型是所有引用类型的零值*

```go
// nil 是一个预先声明的变量，表示 [interface, pointer, slice, map, channel, function] 的零值
var nil Type
```
