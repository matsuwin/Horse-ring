# Struct

<br>

## Go

*example*

```go
package main

import (
	"encoding/json"
	"fmt"
)

type User struct {
	Name string `json:"name"` // Name
	Age  int32  `json:"age"`  // Age
}

func (u *User) print() {
	buf, _ := json.MarshalIndent(u, "", "  ")
	fmt.Printf("%s\n", buf)
	u.Age = 99
}

func main() {
	u := User{}
	u.Name = "Matsuwin"
	u.Age = 24
	u.print()
	fmt.Println(u.Age)
}
```

<br>

## Rust

```rs
