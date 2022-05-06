# Consumer

<br>

***Go***

```go
// new channel, cap=10
var channel = make(chan int, 10)

func consumer() {
    for message := range channel {
        time.Sleep(time.Millisecond * 100)
        fmt.Print(message)
    }
}

func main() {
    go consumer()

    // producer
    for i := 0; i <= 32; i++ {
        channel <- i
    }

    fmt.Println("\nfinish")
    time.Sleep(time.Second * 8)
}
```

<br>

***Kotlin***

```kt
import kotlinx.coroutines.*
import kotlinx.coroutines.channels.*

// new channel, cap=10
val channel = Channel<Int>(10)

suspend fun consumer() {
    for (message in channel) {
        delay(100)
        print(message)
    }
}

suspend fun main() = coroutineScope {

    launch { consumer() }

    // producer
    for (i in 0..32) {
        channel.send(i)
    }

    println("\nfinish")
}
```
