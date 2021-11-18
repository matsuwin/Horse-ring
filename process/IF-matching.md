# IF and matching

<br>

## Go

```go
// Demo code
package main

import "fmt"

func getGrade(score int) (ret int) {
	if score >= 90 {
		ret = 1
	} else if score >= 70 {
		ret = 2
	} else if score >= 60 {
		ret = 3
	} else {
		ret = 4
	}
	return
}

func main() {
	n := getGrade(88)
	g := ""
	switch n {
	case 1: g = "A"
	case 2: g = "B"
	case 3: g = "C"
	case 4: g = "D"
	default: g = "_"
	}
	fmt.Printf("Grade: %s\n", g)
}
```

<br>

## Rust

```rs
// Demo code
fn get_grade(score: i32) -> i32 {
    if score >= 90 {
        return 1;
    } else if score >= 70 {
        return 2;
    } else if score >= 60 {
        return 3;
    } else {
        return 4;
    };
}

fn main() {
    let n = get_grade(88);
    let g = match n {
        1 => "A",
        2 => "B",
        3 => "C",
        4 => "D",
        _ => "_"
    };
    println!("Grade: {}", g);
}
```
