# Exec

<br>

***Go***

```go
import "github.com/utilgo/execve"

func main() {
    text := execve.Args("", []string{"ls", "-l"})
}
```

<br>

***Kotlin***

```kt
fun execve(args: Array<String>): String {
    try {
        val process = Runtime.getRuntime().exec(args)
        var stdout = BufferedReader(InputStreamReader(process.inputStream)).readText()
        val stderr = BufferedReader(InputStreamReader(process.errorStream)).readText()
        stdout = stdout.trim()
        if (stderr != "") {
            stdout += "\n" + stderr.trim()
        }
        return stdout

    } catch (_: Exception) {
    }   
    return ""
}
```
```kt
val text = execve(arrayOf("ls", "-l"))
```

<br>

***Python***


```py
text = os.popen("ls -l").read()
```

<br>

***Rust***

```rs
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
```
```rs
let text = args(".", vec!["ls", "-l"]);
```
