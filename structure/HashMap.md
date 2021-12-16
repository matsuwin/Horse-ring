# HashMap

<br>

*https://go.dev*

```go
// new hashmap
var sets = make(map[int]int)

// write
for i := 0; i < 10; i++ {
	sets[i] = i + 1
}

// show len
fmt.Printf("len %d\n", len(sets))

// range
for key, value := range sets {
	fmt.Printf("%d: %d\n", key, value)
}

// delete
delete(sets, 0)
```

<br>

*https://rustup.rs*

```rs
// new hashmap
let mut hmap: HashMap<i32, i32> = HashMap::new();

// write
for i in 0..10 {
	hmap.insert(i, i + 1);
}

// shwo len and cap
println!("len: {}, cap: {}", hmap.len(), hmap.capacity());

// range
for (key, value) in hmap.iter() {
	println!("{}-{}", key, value);
}
```
