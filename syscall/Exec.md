# Exec

<br>

*https://go.dev*

```go
// Demo code

text := args("", []string{"ls", "-l"})
```
```go
func args(dir string, commands []string) (_ string) {
	if len(commands) == 0 {
		return
	}
	var out, err bytes.Buffer
	cmd := exec.Command(commands[0])
	cmd.Stdout, cmd.Stderr = &out, &err
	cmd.Args = commands
	if dir != "" {
		cmd.Dir = dir
	}
	_ = cmd.Run()
	text := out.String()
	if err.Len() != 0 {
		text += "\n" + err.String()
	}
	if runtime.GOOS == "windows" {
		// text = _GBK(text)
	}
	return strings.TrimSpace(text)
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

fn args(dir: &str, commands: Vec<&str>) -> String {
    if commands.len() == 0 {
        return String::new();
    }
    let mut dir2 = &dir;
    if dir == "" {
        dir2 = &".";
    }
    let cmd = std::process::Command::new("ls")
        .current_dir(&dir2)
        .args(&commands[1..]).output().expect("failed to execute process");
    let mut out = String::from_utf8(cmd.stdout).unwrap();
    let err = String::from_utf8(cmd.stderr).unwrap();
    if err != "" {
        out += &err;
    }
    out.trim().to_string()
}

fn main() {
    let text = args(".", vec!["ls", "-l"]);
    println!("{}", text);
}
```
