# Parallel control

<br>

术语 | 英文 | 定义&描述
|---|---|---|
**进程** | Process | *操作系统中程序的最小单元，进程中有多个线程同时工作。*
**线程** | Thread | *CPU 执行程序的最小单元，线程使用分时调度模式。*
**分时调度** | Time-sharing | *让所有的线程轮流获得 CPU 的使用权，平均分配每个线程占用的 CPU 的时间片。*
**线程安全** | Thread safe | *多个线程访问同一个对象时，可以获得正确的行为结果*
**协程** | Coroutine | *由程序自身实现的多任务调度模型，协程建立在线程之上。*

<br>

*https://go.dev*

```go
func worker(wg *sync.WaitGroup, i int) {
	defer wg.Done()
	fmt.Println(i)

    // 线程不安全的计算
    // index++

    // 线程安全的计算
    // atomic.AddInt32(&index, 1)

    // 使用 sync.Mutex 临界区锁开辟一个线程安全的代码空间
    // mx.Lock()
    // index++
    // mx.Unlock()
}
```
```go
// new controller
var wg = &sync.WaitGroup{}

// add worker
for i := 0; i < 10; i++ {
	wg.Add(1)
	go worker(wg, i)
}

// 等待所有 worker 工作结束
wg.Wait()
```

<br>

*https://rustup.rs*

```rs
// Demo code

use futures::executor::block_on;

async fn hello_world() {
    println!("hello, world!");
}

fn main() {
    let future = hello_world(); // Nothing is printed
    println!("----------------------");
    block_on(future); // `future` is run and "hello, world!" is printed
}
```
