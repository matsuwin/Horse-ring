# System signal

<br>

*https://go.dev*

```go
// Demo code

func main() {
	sig := make(chan os.Signal)
	signal.Notify(sig, syscall.SIGINT, syscall.SIGTERM)

	// Wait
	for message := range sig {
		fmt.Println(message.String())
		return
	}
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

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
