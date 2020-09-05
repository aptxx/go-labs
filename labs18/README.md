测试switch和回调函数效率差异。

实验结果：

```
$ go test -bench="." ./labs18
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs18
Benchmark_UseSwitch-4           265054311                4.42 ns/op
Benchmark_UseCallback-4         472585510                2.54 ns/op
PASS
ok      github.com/aptxx/go-labs/labs18 3.103s
```
