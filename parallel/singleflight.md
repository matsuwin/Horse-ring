# Singleflight

<br>

使用方法

```go
// new controller
var sg = &singleflight.Group{}

// Do Your function
result, err, _ := sg.Do("handlerTag", func() (interface{}, error) {
	return HandlerFunc()
})
```

<br>

测试用例

```go
package main

import (
    "fmt"
    "golang.org/x/sync/singleflight"
    "sync"
    "sync/atomic"
    "time"
)

/**
 * 合并相同动作，减轻查询负载。
 */

var wg = &sync.WaitGroup{}
var sg = &singleflight.Group{}

var sleepDuration int32

// 假设这个是一个数据库查询，比如获取文章信息。
func selectData() (string, error) {
    atomic.AddInt32(&sleepDuration, int32(time.Millisecond))
    time.Sleep(time.Duration(sleepDuration))
    return "detail", nil
}

// 普通调用
func callSelectData() {
    defer wg.Done()
    result, err := selectData()
    if err != nil {
        panic(err)
    }
    _ = result
}

// singleflight 调用
func callSelectDataSg() {
    defer wg.Done()
    result, err, _ := sg.Do("1", func() (interface{}, error) {
        return selectData()
    })
    if err != nil {
        panic(err)
    }
    _ = result
}

func main() {
    start := time.Now()

    // 模拟一千个人在浏览这篇文章
    for i := 0; i < 1000; i++ {
        wg.Add(1)
        //go callSelectData()
        go callSelectDataSg()
    }
    wg.Wait()
    fmt.Printf("耗时: %v\n", time.Now().Sub(start))
}
```
