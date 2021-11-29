# Atomic computing

<br>

*https://go.dev*

```go
// Demo code

var index int32

func main() {
	wg := sync.WaitGroup{}
	for i := 0; i < 1000; i++ {
		wg.Add(1)
		go func(i int) {
			defer wg.Done()
			atomic.AddInt32(&index, 1)
		}(i)
	}
	wg.Wait()
	fmt.Printf("index: %d\n", index)
}
```

<br>

*https://rustup.rs*
