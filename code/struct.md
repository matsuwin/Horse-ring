# Struct

<br>

***Go***

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

// 对象内存分配在堆上，底层调用 runtime.newobject() 申请内存。参数传递时复用内存地址。
user := &User{}

// 对象内存分配在栈上，特定场景下会存在栈空间不足的情况。
// 参数传递时无法复用内存地址，特定场景下会增加对象分配，造成 GC 压力。
user := User{}

user.Name = "matsuwin"
user.Age = 24
user.print()
```
```go
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
