# System signal

<br>

## Go

```go
package main

import (
	"fmt"
	"os"
	"os/signal"
	"syscall"
)

var sig = make(chan os.Signal)

func main() {
	signal.Notify(sig, syscall.SIGINT, syscall.SIGTERM)

    // Wait
	for message := range sig {
		fmt.Println(message.String())
		return
	}
}
```

<br>

## Rust

```rs
#[macro_use]
extern crate chan;

use chan_signal::Signal;

fn main() {
    let signal = chan_signal::notify(&[Signal::INT, Signal::TERM]);

    // Wait
    chan_select! {
        signal.recv() -> signal => {
            println!("received signal: {:?}", signal)
        },
    }
}
```
