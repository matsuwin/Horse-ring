# Critical section lock

<br>

*https://go.dev*

```go
// Demo code

var index int32

func main() {
	mx := sync.Mutex{}
	wg := sync.WaitGroup{}
	for i := 0; i < 1000; i++ {
		wg.Add(1)
		go func(i int) {
			defer wg.Done()
			mx.Lock()
			index++
			mx.Unlock()

		}(i)
	}
	wg.Wait()
	fmt.Printf("index: %d\n", index)
}
```
<br>

*https://rustup.rs*
