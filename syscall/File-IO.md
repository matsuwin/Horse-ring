# File I/O

<br>

*https://go.dev*

```go
// 打开文件
fop, err := os.Open("1.txt")
if err != nil {
	panic(err)
}

// 读取数据
data, _ := ioutil.ReadAll(fop)

// 关闭文件
fop.Close()

// 打印数据
fmt.Printf("%s\n", data)

// 写入新文件
fcr, _ := os.Create("2.txt")
fcr.Write(data)
fcr.Close()
```

<br>

*https://rustup.rs*

```rs
// 打开文件
let mut fop = match std::fs::File::open("1.txt") {
    Err(err) => panic!("{}", err),
    Ok(file) => file,
};

// 读取数据
let mut data = String::new();
fop.read_to_string(&mut data).unwrap();

// 关闭文件

// 打印数据
println!("{}", data);

// 写入新文件
let mut fcr = std::fs::File::create("2.txt".to_string()).unwrap();
fcr.write_all(data.as_bytes()).unwrap();
```

<br>

*https://dart.dev*

```dart
// 打开文件
var fop = new File("1.txt");

// 读取数据
var data = fop.readAsStringSync().toString();

// 关闭文件

// 打印数据
print(data);

// 写入新文件
File fcr = new File("2.txt");
fcr.writeAsStringSync(data);
```
