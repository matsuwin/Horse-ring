# IF and matching

<br>

*https://go.dev*

```go
// Demo code

func condition(score int) rune {
	if score >= 80 {
		return 'A'
	} else if score >= 60 {
		return 'B'
	} else {
		return 'C'
	}
}

func matching(score int) string {
	switch condition(score) {
	case 'A':
		return "优秀"
	case 'B':
		return "及格"
	case 'C':
		return "不及格"
	default:
		return "?"
	}
}

func main() {
	fmt.Printf("成绩%s\n", matching(88))
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

fn condition(score: i32) -> char {
    if score >= 80 {
        return 'A';
    } else if score >= 60 {
        return 'B';
    } else {
        return 'C';
    }
}

fn matching(score: i32) -> String {
    match condition(score) {
        'A' => "优秀",
        'B' => "及格",
        'C' => "不及格",
        _ => "?"
    }.to_string()
}

fn main() {
    println!("成绩{}", matching(88));
}
```
