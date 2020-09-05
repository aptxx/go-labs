测试匿名函数和普通函数的调用消耗。

禁用优化前：

```
$ go test -test.bench="." ./labs09
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs09
Benchmark_NormalFuncCall-4      1000000000               0.277 ns/op
Benchmark_VarFuncCall1-4        1000000000               0.282 ns/op
Benchmark_VarFuncCall2-4        837052402                1.39 ns/op
PASS
ok      github.com/aptxx/go-labs/labs09 1.945s
```

禁用优化后：

```
$ go test -test.bench="." -gcflags '-N' ./labs09
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs09
Benchmark_NormalFuncCall-4      632374074                1.92 ns/op
Benchmark_VarFuncCall1-4        394213730                3.04 ns/op
Benchmark_VarFuncCall2-4        429071910                2.76 ns/op
PASS
ok      github.com/aptxx/go-labs/labs09 4.394s
```

结论：测试中用的是一个很简单的函数，所以很容易被新版的go做内联优化，禁用优化前后结果差别明显，如果不考虑优化，匿名函数和普通函数调用差别甚微。但是普通函数比较有可能被优化。在没有优化的情况下，闭包函数消耗又要再高一个量级。