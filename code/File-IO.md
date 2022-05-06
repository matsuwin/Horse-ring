# File I/O stream

<br>

***Go***

```go
// 打开原始文件
src, err := os.Open("1.txt")
if err != nil {
	panic(err)
}

// 读取数据到内存
// data, _ := io.ReadAll(src)
// fmt.Printf("%s\n", data)

// 创建目标文件
dst, _ := os.Create("2.txt")

// 拷贝数据
_, _ = io.Copy(dst, src)

// 关闭文件
dst.Close()
src.Close()
```

<br>

***Kotlin***

```kt
// 打开原始文件
val src = File("1.txt").inputStream()

// 读取数据到内存
// val data = src.reader().readText()
// println(data)

// 创建目标文件
val dst = File("2.txt").outputStream()

// 拷贝数据
src.copyTo(dst)

// 关闭文件
dst.close()
src.close()
```

<br>

***Python***

```py
import shutil

# 打开原始文件
src = open("main.py", "rb")

# 读取数据到内存
# data = src.read()
# print(data)

# 创建目标文件
dst = open("main.txt", "wb")

# 拷贝数据
shutil.copyfileobj(src, dst)

# 关闭文件
dst.close()
src.close()
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
