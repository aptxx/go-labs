比较直接调用函数和反射调用函数的效率差别，忘记为什么目的测试的了。

测试结果：

```
$ go test -bench="." ./labs26
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs26
Benchmark_NormalFuncCall-4      1000000000               0.279 ns/op
Benchmark_ReflectFuncCall-4      3466174               360 ns/op
PASS
ok      github.com/aptxx/go-labs/labs26 1.918s
```