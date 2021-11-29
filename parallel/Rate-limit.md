# Rate limit

<br>

## Go

*https://go.dev*

```go
// Demo code

package main

import "go.uber.org/ratelimit"

func main() {
	rl := ratelimit.New(20) // 速率, r/s
	for i := 0; i < 100; i++ {
		rl.Take()
		fmt.Print(i)
	}
}
```

<br>

*https://rustup.rs*
