# Channel queue

<br>

## Go

*/usr/local/go/src/runtime/chan.go*

```go
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

*example*

```go
var wait = make(chan int)
go func() {
	time.Sleep(time.Second)
	wait <- 1
}()
<-wait
```
```go
var queue = make(chan int, 100)

go func() {
	for i := 0; i < 100; i++ {
		queue <- i
	}
	fmt.Println("End of filling")
}()

for message := range queue {
	time.Sleep(time.Millisecond * 10)
	fmt.Print(message)
}
```
