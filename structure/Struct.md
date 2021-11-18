# Struct

<br>

## Go

```go
// Source code
```
```go
// Demo code
package main

type User struct {
	Name string `json:"name"` // Name
	Age  uint32 `json:"age"`  // Age
}

func (u *User) print() {
	buf, _ := json.MarshalIndent(u, "", "  ")
	fmt.Printf("%s\n", buf)
	u.Age = 99
}

func main() {
	u := User{}
	u.Name = "Matsuwin"
	u.Age = 24
	u.print()
	fmt.Println(u.Age)
}
```

<br>

## Rust

```rs
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
