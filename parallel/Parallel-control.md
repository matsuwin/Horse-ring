# Parallel control

<br>

## Go

```
GMP
```

*example*

```go
wg := sync.WaitGroup{}

for i := 0; i < 10; i++ {
	wg.Add(1)
	go func(i int) {
		defer wg.Done()
		fmt.Println(i)
	}(i)
}

wg.Wait()
```
