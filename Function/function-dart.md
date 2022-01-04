# Function

<br>

```dart
import 'dart:io';

// 匿名函数
var f1 = () {
  print("f1");
};

// 命名函数
void f2() {
  print("f2");
}

// 不限长参数
void f3(a) {
  print(a);
}

// 任意类型参数
void f4(a) {
  print(a);
}

// 多返回值
Tuple2<int, String> demo() {
  return new Tuple2(42, "life is good");
}

// func f5() (n1, n2 int, _ error) {
// fmt.Println("f5")
// return 2, 3, nil
// }

void main() {
  stdout.write("Hello World\n");

  // 延迟函数
  // defer func() {
  //   fmt.Println("延迟函数")
  // }()

  // 自执行函数
  () {
    print("自执行函数");
  }();

  f1();
  f2();
  // f3(1, 2, 3, 4)
  f4("");
  // n1, n2, _ := f5()
  // fmt.Println(n1, n2)
}
```
