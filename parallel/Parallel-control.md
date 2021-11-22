# Parallel control

<br>

**进程**

*操作系统中程序的最小单元，进程中有多个线程同时工作。*

**线程**

*CPU*

**分时调度**

**协程**

*程序自身实现的调度模型，建立在线程之上。*

<br>

## Go

```go
// Demo code
var wg = &sync.WaitGroup{}

for i := 0; i < 10; i++ {
	wg.Add(1)
	go func(i int) {
		defer wg.Done()
		fmt.Println(i)
	}(i)
}

wg.Wait()
```
