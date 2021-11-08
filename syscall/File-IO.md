# File I/O

<br>

## Go

```go
filename := "main.go"

// 打开文件
fis, err := os.Open(filename)
if err != nil {
	panic(err)
}

// 读取数据
data, _ := ioutil.ReadAll(fis)

// 关闭文件
fis.Close()

// 打印数据
fmt.Printf("%s\n", data)

// 写入新文件
fos, _ := os.Create(filename + ".txt")
_, _ = fos.Write(data)
_ = fos.Close()
```

<br>

## Rust

```rs
use std::io::{Read, Write};

fn main() {
    let filename = "src/main.rs";

    // 打开文件
    let mut fo = match std::fs::File::open(filename) {
        Err(err) => panic!("{}", err),
        Ok(file) => file,
    };

    // 读取数据
    let mut data = String::new();
    fo.read_to_string(&mut data).unwrap();

    // 关闭文件

    // 打印数据
    println!("{}", data);

    // 写入新文件
    let mut fc = std::fs::File::create(filename.to_string() + ".txt").unwrap();
    fc.write_all(data.as_bytes()).unwrap();
}
```
