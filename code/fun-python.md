# Function

<br>

```py
# 匿名函数
f1 = lambda: print("f1")

# 命名函数
def f2(): print("f2")

# 不限长参数
def f3(*a): print("f3", a)

# 任意类型参数
def f4(a): print("f4", type(a))

# 多返回值
def f5(): return 2, 3

if __name__ == '__main__':

    # 自执行函数
    (lambda: print("自执行函数"))()

    f1()
    f2()
    f3(1, 2, 3, 4)
    f4("")
    n1, n2 = f5()
    print("f5", n1, n2)
```
```
自执行函数
f1
f2
f3 (1, 2, 3, 4)
f4 <class 'str'>
f5 2 3
```
