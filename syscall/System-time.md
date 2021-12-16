# System time

<br>

*https://go.dev*

```go
var unixMillis = time.Now().UnixMilli()
var timeString = time.UnixMilli(unixMillis).Local().Format(time.RFC3339Nano)
```

<br>

*https://dart.dev*

```dart
var unixMillis = DateTime.now().millisecondsSinceEpoch;
var timeString = DateTime.fromMillisecondsSinceEpoch(unixMillis);
```

<br>

*https://rustup.rs*

```rs
use chrono::{Local, TimeZone};

fn main() {
    let unix_millis = Local::now().timestamp_millis();
    let time_string = Local.timestamp_millis(unix_millis).to_rfc3339();
    println!("{}", unix_millis);
    println!("{}", time_string);
}
```
