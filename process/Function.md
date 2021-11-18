# Function

<br>

## Go

```go
// Source code
```
```go
// Demo code
package main

// 匿名函数
var f1 = func() { fmt.Println("f1") }

// 命名函数
func f2() { fmt.Println("f2") }

// 不限长参数
func f3(a ...int) { fmt.Println("f3", a) }

// 任意类型参数
func f4(a interface{}) { fmt.Printf("f4 %T\n", a) }

// 多返回值
func f5() (n1, n2 int, _ error) {
	fmt.Println("f5")
	return 2, 3, nil
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
	n1, n2, _ := f5()
	fmt.Println(n1, n2)
}
```

<br>

## Rust

*example*

```rs
use defer_lite::defer;

fn type_of<T>(_: &T) -> String {
    std::any::type_name::<T>().to_string()
}

// 命名函数
fn f2() { println!("f2") }

// 任意类型参数
fn f4<T>(a: T) { println!("f4 {}", type_of(&a)) }

// 多返回值
fn f5() -> (i32, i32) {
    println!("f5");
    (2, 3)
}

fn main() {

    // 延迟函数
    defer! {
        println!("延迟函数")
    }

    // 匿名函数
    let f1 = || { println!("f1") };

    f1();
    f2();
    f4("");
    let (n1, n2) = f5();
    println!("{} {}", n1, n2);
}
```
