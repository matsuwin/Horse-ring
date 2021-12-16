# Slice

<br>

*https://go.dev*

```go
// source code src/runtime/slice.go
type slice struct {
	array unsafe.Pointer
	len   int
	cap   int
}
```
```go
// new slice
var slice = make([]int, 0, 0)

// write
for i := 2; i <= 512; i++ {
	i = i * 2
	slice = append(slice, i)
	i--
}

// shwo len and cap
fmt.Printf("len %d, cap %d\n", len(slice), cap(slice))

// range
for i := range slice {
	fmt.Printf("%d ", slice[i])
}
```

<br>

*https://rustup.rs*

```rs
// new slice
let mut slice: Vec<i32> = vec![];

// write
for mut i in 2..=512 {
	i = i * 2;
	slice.push(i);
	i = i - 1;
}

// show len and cap
println!("len: {}, cap: {}", slice.len(), slice.capacity());

// range
for i in 0..slice.len() {
	print!("{} ", i);
    io::stdout().flush();
}
```
