# String

<br>

***String utils***

| 功能描述 | Go | Kotlin | Rust |
|---:|---|---|---|
| 判断是否包含 | strings.Contains || "".contains
| 前缀匹配 | strings.HasPrefix ||
| 后缀匹配 | strings.HasSuffix ||
| 前缀修剪 | strings.TrimPrefix || "".strip_prefix
| 后缀修剪 | strings.TrimSuffix || "".strip_suffix
| 修剪头尾空格 | strings.TrimSpace || "".trim
| 字符串拆分 | strings.Split ||
| 字符串拼接 | strings.Join || "".join`
| 字符串替换 | strings.ReplaceAll || "".replace
| 字母转小写 | strings.ToLower || "".to_lowercase
| 字母转大写 | strings.ToUpper || "".to_uppercase
| 字段拆分 | strings.Fields ||
| 统计字符出现的次数 | strings.Count ||

<br>

***Go***

```go
// source code src/runtime/string.go
type stringStruct struct {
	str unsafe.Pointer
	len int
}
```
```go
// range
for _, char := range "你好世界" {
	fmt.Printf("%c ", char)
}
```
```go
// buffer
buf := bytes.Buffer{}
buf.Write([]byte(""))
```

<br>

***Kotlin***

```kt
// range
for (char in "你好世界") {
    print(char)
}
```

<br>

*https://rustup.rs*

```rs
// range
let text = "你好世界";
for char in text.chars() {
	println!("{}", char);
}
```
```rs
// buffer
let mut buf = String::new();
buf.write_str("").unwrap();
```
