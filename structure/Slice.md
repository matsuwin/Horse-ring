# Slice

<br>

## Go

```go
// Source code src/runtime/slice.go
type slice struct {
	array unsafe.Pointer
	len   int
	cap   int
}
```
```go
// Demo code
var slice = make([]int, 0, 0)

for i := 2; i <= 512; i++ {
	i = i * 2
	slice = append(slice, i)
	i--
}

fmt.Printf("len %d, cap %d\n", len(slice), cap(slice))

for i := range slice {
	fmt.Printf("%d ", slice[i])
}
```

<br>

## Rust

*example*

```rs
let mut slice: Vec<i32> = vec![];
for i in 0..10 {
    slice.push(i + 1);
}
println!("len: {}, cap: {}", slice.len(), slice.capacity());

for i in 0..slice.len() {
    println!("{}-{}", i, slice[i]);
}
```
