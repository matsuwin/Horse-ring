# Basic type

Basic type: Boolean, Int, Uint, Float

<br>

## Go

*/usr/local/go/src/builtin/builtin.go*

```go
type bool bool             // boolean values, true and false.
type uint8 uint8           // Range: 0 through 255.
type uint16 uint16         // Range: 0 through 65535.
type uint32 uint32         // Range: 0 through 4294967295.
type uint64 uint64         // Range: 0 through 18446744073709551615.
type uint uint             // OSBit: uint32 or uint64
type int8 int8             // Range: -128 through 127.
type int16 int16           // Range: -32768 through 32767.
type int32 int32           // Range: -2147483648 through 2147483647.
type int64 int64           // Range: -9223372036854775808 through 9223372036854775807.
type int int               // OSBit: int32 or int64
type float32 float32       // IEEE-754 32-bit floating-point numbers.
type float64 float64       // IEEE-754 64-bit floating-point numbers.
type complex64 complex64   // complex numbers with float32 real and
type complex128 complex128 // complex numbers with float64 real and
type byte = uint8          // byte is an alias for uint8
type rune = int32          // rune is an alias for int32
```

*example*

```go
func main() {
	var num int32
	fmt.Printf("%T:%d\n", num, num)
}

// int32:0
```

<br>

## Rust

```rs
```

*example*

```rs
fn type_of<T>(_: &T) -> String {
    std::any::type_name::<T>().to_string()
}

fn main() {
    let num: i32 = 0;
    println!("{}:{}", type_of(&num), num);
}

// i32:0
```
