# Parallel control

<br>

**进程**

*操作系统中程序的最小单元，进程中有多个线程同时工作。*

**线程**

*CPU 执行程序的最小单元，线程使用分时调度模式。*

**分时调度**

*让所有的线程轮流获得 CPU 的使用权，平均分配每个线程占用的 CPU 的时间片。*

**协程**

*由程序自身实现的多任务调度模型，协程建立在线程之上。*

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
