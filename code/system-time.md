# System time

<br>

***Go***

```go
var unixMillis = time.Now().UnixMilli()
var timeString = time.UnixMilli(unixMillis).Local().Format(time.RFC3339Nano)
```

<br>

***Kotlin***

```kt
val unixMillis = System.currentTimeMillis()
val timeString = SimpleDateFormat("yyyy-MM-dd'T'h:m:ss.SSSZ").format(Date(unixMillis))
```

<br>

***Python***

```py
unixMillis = int(datetime.timestamp(datetime.now()) * 1000)
timeString = datetime.fromtimestamp(unixMillis / 1000)
```

<br>

***Dart***

```dart
var unixMillis = DateTime.now().millisecondsSinceEpoch;
var timeString = DateTime.fromMillisecondsSinceEpoch(unixMillis);
```

<br>

***Rust***

```rs
use chrono::{Local, TimeZone};

fn main() {
    let unix_millis = Local::now().timestamp_millis();
    let time_string = Local.timestamp_millis(unix_millis).to_rfc3339();
    println!("{}", unix_millis);
    println!("{}", time_string);
}
```
