# System signal

<br>

***Go***

```go
sig := make(chan os.Signal)
signal.Notify(sig, syscall.SIGINT, syscall.SIGTERM)

// Wait
for message := range sig {
    fmt.Println(message.String())
    return
}
```

<br>

***Kotlin***

```kt
import sun.misc.Signal
import kotlin.system.exitProcess

fun main() {
    for (sig in arrayOf("INT", "TERM")) {
        Signal.handle(Signal(sig)) {
            println(it.toString())
            exitProcess(0)
        }
    }
    while (true) {
        Thread.sleep(5000)
    }
}
```

<br>

***Python***

```py
import signal


def handler(signum, frame):
    print('I received: ', signum)


signal.signal(signal.SIGINT, handler)
signal.signal(signal.SIGTERM, handler)
signal.pause()
```

<br>

***Rust***

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
