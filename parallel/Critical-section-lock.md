# Critical section lock

<br>

*example*

```go
var index int32

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
```
