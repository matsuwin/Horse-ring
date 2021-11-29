# Channel queue

<br>

*https://go.dev*

```go
// Source code src/runtime/chan.go
type hchan struct {
	qcount   uint           // total data in the queue
	dataqsiz uint           // size of the circular queue
	buf      unsafe.Pointer // points to an array of dataqsiz elements
	elemsize uint16
	closed   uint32
	elemtype *_type // element type
	sendx    uint   // send index
	recvx    uint   // receive index
	recvq    waitq  // list of recv waiters
	sendq    waitq  // list of send waiters

	// lock protects all fields in hchan, as well as several
	// fields in sudogs blocked on this channel.
	//
	// Do not change another G's status while holding this lock
	// (in particular, do not ready a G), as this can deadlock
	// with stack shrinking.
	lock mutex
}
```
```go
// Demo code

func main() {
	wait := make(chan int)
	go func() {
		time.Sleep(time.Second)
		wait <- 1
	}()
	<-wait
}
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
