# File I/O

<br>

*https://go.dev*

```go
// Demo code

const fp = "main.go"

func main() {

	// 打开文件
	fo, err := os.Open(fp)
	if err != nil {
		panic(err)
	}

	// 读取数据
	data, _ := ioutil.ReadAll(fo)

	// 关闭文件
	fo.Close()

	// 打印数据
	fmt.Printf("%s\n", data)

	// 写入新文件
	fc, _ := os.Create(fp + ".txt")
	fc.Write(data)
	fc.Close()
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

use std::io::{Read, Write};

fn main() {
    let fp = "src/main.rs";

    // 打开文件
    let mut fo = match std::fs::File::open(fp) {
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
    let mut fc = std::fs::File::create(fp.to_string() + ".txt").unwrap();
    fc.write_all(data.as_bytes()).unwrap();
}
```
