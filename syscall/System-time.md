# System time

<br>

*https://go.dev*

```go
// Demo code

func main() {
	unixMillis := time.Now().UnixMilli()
	timeString := time.UnixMilli(unixMillis).Local().Format(time.RFC3339Nano)
	fmt.Println(unixMillis)
	fmt.Println(timeString)
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

use chrono::{Local, TimeZone};

fn main() {
    let unix_millis = Local::now().timestamp_millis();
    let time_string = Local.timestamp_millis(unix_millis).to_rfc3339();
    println!("{}", unix_millis);
    println!("{}", time_string);
}
```
