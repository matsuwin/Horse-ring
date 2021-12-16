# Standard I/O

<br>

```sh
# 重定向标准输出到文件
./main 1> 1.txt # or ./main > 1.txt

# 重定向标准错误到文件
./main 2> 1.txt
```

<br>

*https://dart.dev*

```dart
// input
var input = stdin.readLineSync();

// output
stdout.write("stdout ${input}\n");
stderr.write("stderr ${input}\n");
```

<br>

*https://go.dev*

```go
// input
input := ""
fmt.Scan(&input)

// output
fmt.Println("stdout " + input)
println("stderr " + input)
```

<br>

*https://rustup.rs*

```rs
// input
let mut input = String::new();
io::stdin().read_line(&mut input);

// output
println!("stdout");
eprintln!("stderr");
```
