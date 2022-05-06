# Standard I/O

<br>

***System***

```sh
# 重定向标准输出到文件
./main 1> 1.txt # or ./main > 1.txt

# 重定向标准错误到文件
./main 2> 1.txt
```

<br>

***Clang***

```c
// output
fprintf(stdout, "stdout\n"); // printf();
fprintf(stderr, "stderr\n");
```

<br>

***Go***

```go
// input
fmt.Scan(&input)

// output
fmt.Fprintf(os.Stdout, "stdout\n") // fmt.Printf()
fmt.Fprintf(os.Stderr, "stderr\n")
```

<br>

***Kotlin***

```kt
// input
val input = readLine()

// output
System.out.print("stdout\n") // print()
System.err.print("stderr\n")
```

<br>

***Python***

```py
# input
value = input()

# output
sys.stdout.write("stdout\n") # print()
sys.stderr.write("stderr\n")
```

<br>

***Rust***

```rs
// input
let mut input = String::new();
io::stdin().read_line(&mut input);

// output
print!("stdout\n");
eprintln!("stderr");
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

*https://vlang.io*

```go
// input
name := os.input("input: ")

// output
print("stdout $name\n")
eprintln("stderr")
```
