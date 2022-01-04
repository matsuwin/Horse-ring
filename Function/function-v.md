# Function

<br>

```v
// 命名函数
fn f2() {
	println('f2')
}

// 不限长参数
fn f3(a ...int) {
	println(a)
}

// 任意类型参数
// fn f4(a any) { println(a) }

// 多返回值
fn f5() (int, int) {
	println('f5')
	return 2, 3
}

fn main() {

	// 匿名函数
	f1 := fn () {
		println('f1')
	}

	// 延时函数
	defer {
		println('延时函数')
	}

	// 自执行函数
	fn () {
		println('自执行函数')
	}()

	f1()
	f2()
	f3(1, 2, 3, 4)
	// f4("")
	n1, n2 := f5()
	println('$n1 $n2')
}
```
