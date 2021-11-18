# HashMap

<br>

## Go

```go
// Source code src/runtime/map.go
type hmap struct {
	count      int // # live cells == size of map.  Must be first (used by len() builtin)
	flags      uint8
	B          uint8          // log_2 of # of buckets (can hold up to loadFactor * 2^B items)
	noverflow  uint16         // approximate number of overflow buckets; see incrnoverflow for details
	hash0      uint32         // hash seed
	buckets    unsafe.Pointer // array of 2^B Buckets. may be nil if count==0.
	oldbuckets unsafe.Pointer // previous bucket array of half the size, non-nil only when growing
	nevacuate  uintptr        // progress counter for evacuation (buckets less than this have been evacuated)
	extra      *mapextra      // optional fields
}
```
```go
// Demo code
var sets = make(map[int]int, 10)

for i := 0; i < 10; i++ {
	sets[i] = i + 1
}

fmt.Printf("len %d\n", len(sets))

for key, value := range sets {
	fmt.Printf("%d: %d\n", key, value)
}
```

<br>

## Rust

*example*

```rs
use std::collections::HashMap;

fn main() {
    let mut hmap: HashMap<i32, i32> = HashMap::new();
    for i in 0..10 {
        hmap.insert(i, i + 1);
    }
    println!("len: {}, cap: {}", hmap.len(), hmap.capacity());

    for (key, value) in hmap.iter() {
        println!("{}-{}", key, value);
    }
}
```
