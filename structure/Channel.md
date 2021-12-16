# Channel queue

<br>

*https://go.dev*

```go
// new channel
var wait = make(chan int)

// 一秒钟后向 channel 中写入数据
go func() {
	time.Sleep(time.Second)
	wait <- 1
}()

// 从 channel 中取数据，如果没有数据会一直阻塞，直到有数据写入。
<-wait
```

```go
// message queue

var queue = make(chan int, 10)

func consumer() {
	for message := range queue {
		fmt.Print(message)
		time.Sleep(time.Millisecond * 100)
	}
}

func main() {
	go consumer()
	for i := 0; i < 100; i++ {
		queue <- i
	}
}
```

<br>

*https://rustup.rs*
