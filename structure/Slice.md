# Slice

<br>

## Go

*/usr/local/go/src/runtime/slice.go*

```go
type slice struct {
	array unsafe.Pointer
	len   int
	cap   int
}
```

*example*

```go
slice := make([]int, 0, 0)
for i := 0; i < 10; i++ {
	slice = append(slice, i+1)
}
fmt.Printf("len: %d, cap: %d\n", len(slice), cap(slice))

for i := range slice {
	fmt.Printf("%d-%d\n", i, slice[i])
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
