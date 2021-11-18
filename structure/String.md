# String

<br>

## Go

```go
// Source code src/runtime/string.go
type stringStruct struct {
	str unsafe.Pointer
	len int
}
```
```go
// Demo code
var text = "你好世界"
for _, char := range text {
    fmt.Printf("%c ", char)
}
```

*Utils*

```go
strings.Contains("Hello,World", ",Wo")        // 判断是否包含字符
strings.HasPrefix("Hello,World", "He")        // 前缀匹配
strings.HasSuffix("Hello,World", "ld")        // 后缀匹配
strings.TrimPrefix("Hello,World", "Hello")    // 前缀修剪
strings.TrimSuffix("Hello,World", "World")    // 后缀修剪
strings.TrimSpace(" Hi ")                     // 修剪头尾空格
strings.Split("Hello,World", ",")             // 字符串拆分
strings.Join([]string{"Hello", "World"}, ",") // 字符串拼接
strings.ReplaceAll("Hello,World", ",", "/")   // 字符串替换
strings.ToLower("Hello,World")                // 字母转小写
strings.ToUpper("Hello,World")                // 字母转大写

strings.Fields("Hello World")                 // 字段拆分
strings.Count("Hello,World", "l")             // 统计字符出现的次数
strings.Index("Hello,World", "l")             // 左边开始第一个匹配的索引
strings.LastIndex("Hello,World", "l")         // 右边开始第一个匹配的索引
```

*Buffer*

```go
// Buffer
buf := bytes.Buffer{}
buf.Write([]byte("1"))
buf.Write([]byte("2"))
fmt.Printf("%s\n", buf.Bytes())
```

<br>

## Rust

*Utils*

```rs
println!("{}:{}", type_of(&tag), tag);

println!("{}", tag.contains("Wo"));// 判断是否包含字符
// println!("{}", &tag.is_prefix_of("ld"));// 判断后缀是否匹配
// println!("{}", tag.fiel);// 更具TAB和空格拆分字段
println!("{}", tag.strip_prefix("Hello").unwrap());// 修剪前缀
println!("{}", tag.strip_suffix("World").unwrap());// 修剪后缀
println!("{}", tag.trim());// 修剪头尾空格
// println!("{}", tag.split(","));// 字符串拆分
println!("{}", ["Hello", "World"].join(","));// 字符串拼接
println!("{}", tag.replace(",", "/"));// 字符串替换
println!("{}", tag.to_lowercase());// 转小写字母
println!("{}", tag.to_uppercase());// 转大写字母
```

*Buffer*

```rs
use std::fmt::Write;

fn main() {
    let mut buf = String::new();
    buf.write_str("1").unwrap();
    buf.write_str("2").unwrap();
    println!("{}", buf.as_str());
}
```
