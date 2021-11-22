# Rate limit

<br>

## Go

*example*

```go
package main

import (
	"fmt"
	"go.uber.org/ratelimit"
)

func main() {
	rl := ratelimit.New(20) // 速率, r/s
	for i := 0; i < 100; i++ {
		rl.Take()
		fmt.Print(i)
	}
}
```
