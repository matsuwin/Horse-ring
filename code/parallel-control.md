# Parallel control

<br>

术语 | 英文 | 定义&描述
|---|---|---|
**进程** | Process | *操作系统中程序的最小单元，进程中有多个线程同时工作。*
**线程** | Thread | *CPU 执行程序的最小单元，线程使用分时调度模式。*
**分时调度** | Time-sharing | *让所有的线程轮流获得 CPU 的使用权，平均分配每个线程占用的 CPU 的时间片。*
**线程安全** | Thread safe | *多个线程访问同一个对象时，可以获得正确的行为结果*
**协程** | Coroutine | *单线程协程，通过挂起和恢复操作进行通信。*
**Go** | Goroutine | *多线程协程，由程序自身实现的多任务并行调度模型，通过 channel 进行通信。*

<br>

***Go***

```go
func worker(wg *sync.WaitGroup, i int) {
	defer wg.Done()

    time.Sleep(time.Millisecond * 500)
	fmt.Println(i)

    // 线程不安全的计算
    // index++

    // 线程安全的计算
    // atomic.AddInt32(&index, 1)

    // 使用 sync.Mutex 临界区锁开辟一个线程安全的代码空间
    // mutex.Lock()
    // index++
    // mutex.Unlock()
}
```
```go
// new controller
var wg = &sync.WaitGroup{}

// add workers
for i := 0; i < 10; i++ {
	wg.Add(1)
	go worker(wg, i)
}

// wait workers to end
wg.Wait()
```

<br>

***Kotlin***

```kt
import kotlinx.coroutines.*
import kotlinx.coroutines.sync.*
```
```kt
suspend fun worker(i: Int) {
    delay(500)
    println(i)

    // 线程不安全的计算
    // index++

    // 使用 sync.Mutex 临界区锁开辟一个线程安全的代码空间
    // mutex.withLock {
    //     index++
    // }
}
```
```kt
suspend fun program() = coroutineScope {

    // add workers
    for (i in 0..9) {
        launch { worker(i) }
    }
}

suspend fun main() = coroutineScope {

    // wait workers to end
    launch { program() }.join()
}
```

<br>

***Python***

```go

```
