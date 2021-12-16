
*https://rustup.rs*

```rs
// Demo code

fn type_of<T>(_: &T) -> String {
    std::any::type_name::<T>().to_string()
}

fn main() {
    let num: i32 = 0;
    println!("{}:{}", type_of(&num), num);
}

// i32:0
```

```rs
usize
u8, u16, u32, u64
i8, i16, i32, i64
&str
String
```
