# System time

<br>

## Go

```go
package main

import (
	"fmt"
	"time"
)

func main() {
	timestamp := time.Now().UnixMilli()
	timeString := time.UnixMilli(timestamp).Local().Format(time.RFC3339Nano)
	fmt.Println(timestamp)
	fmt.Println(timeString)
}
```

<br>

## Rust

```rs
use chrono::{Local, TimeZone};

fn main() {
    let timestamp = Local::now().timestamp_millis();
    let time_string = Local.timestamp_millis(timestamp).to_rfc3339();
    println!("{}", timestamp);
    println!("{}", time_string);
}
```
