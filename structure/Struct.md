# Struct

<br>

*https://go.dev*

```go
type User struct {
	Name string `json:"name"` // Name
	Age  uint32 `json:"age"`  // Age
}

func (u *User) print() {
	buf, _ := json.MarshalIndent(u, "", "  ")
	fmt.Printf("%s\n", buf)
	u.Age = 99
}
```
```go
func main() {
	user := &User{}
	user.Name = "Matsuwin"
	user.Age = 24
	user.print()
	fmt.Println(u.Age)
}
```

<br>

*https://rustup.rs*

```rs
// Demo code

pub struct User {
    pub name: String,
    pub age: u32,
}

impl User {
    pub fn print(&mut self) {
        println!("name: {}", self.name);
        println!("age: {}", self.age);
        self.age = 99;
    }
}

fn main() {
    let mut u = User {
        name: String::from("Matsuwin"),
        age: 24,
    };
    u.print();
    println!("{}", u.age);
}
```
