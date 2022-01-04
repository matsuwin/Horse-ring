# Struct

<br>

*https://go.dev*

```go
type User struct {
    Name string `json:"name"` // Name
    Age  int    `json:"age"`  // Age
}

func (u *User) print() {
    buf, _ := json.MarshalIndent(u, "", "  ")
    fmt.Printf("%s\n", buf)
    u.Age = 99
}
```
```go
// 结构体实例
user := &User{}
user.Name = "matsuwin"
user.Age = 24
user.print()

// 结构体遍历
x := reflect.TypeOf(user).Elem()
v := reflect.ValueOf(user).Elem()
for i := 0; i < x.NumField(); i++ {
    fx := x.Field(i)
    fv := v.Field(i)
    switch fv.Kind() {
    case reflect.String:
        fmt.Printf("%s=%v\n", fx.Name, fv.String())
    case reflect.Int:
        fmt.Printf("%s=%v\n", fx.Name, fv.Int())
    }
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
