# Rate limit

<br>

*https://go.dev*

```go
package main

import "go.uber.org/ratelimit"

/**
 * 限流器的使用
 */

func main() {
    rl := ratelimit.New(20) // 速率, r/s
    for i := 0; i < 100; i++ {
        rl.Take()
        fmt.Print(i)
    }
}
```
