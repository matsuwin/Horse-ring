# Standard I/O

<br>

```sh
# 重定向标准输出到文件
./main 1> 1.txt # or ./main > 1.txt

# 重定向标准错误到文件
./main 2> 1.txt
```

<br>

*C*

```c
// output
fprintf(stdout, "stdout\n"); // or printf("stdout\n");
fprintf(stderr, "stderr\n");
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
var input string
fmt.Scan(&input)

// output
fmt.Printf("stdout %s\n", input)
println("stderr")
```

<br>

*https://vlang.io*

```go
// input
name := os.input("input: ")

// output
print("stdout $name\n")
eprintln("stderr")
```

<br>

*https://rustup.rs*

```rs
// input
let mut input = String::new();
io::stdin().read_line(&mut input);

// output
print!("stdout\n");
eprintln!("stderr");
```
