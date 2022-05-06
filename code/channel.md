# Channel
从 channel 中读取数据时，如果没有数据会一直阻塞，直到有数据写入。

<br>

***Go***

```go
// new channel
var wait = make(chan int)

// write
go func() {
    time.Sleep(time.Second)
    wait <- 1
}()

// read
fmt.Println("wait...")
fmt.Printf("msg=%d\n", <-wait)
```

<br>

***Kotlin***

```kt
import kotlinx.coroutines.*
import kotlinx.coroutines.channels.*

suspend fun main() = coroutineScope {

    // new channel
    val channel = Channel<Int>()

    // write
    launch {
        delay(1000)
        channel.send(1)
    }

    // read
    println("wait...")
    println("msg=${channel.receive()}")
}
```
