# Atomic computing

<br>

## Go

*example*

```go
var index int32

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
```
