# Function

<br>

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
