测试range循环和for循环，以及结构体循环和指针循环的性能区别。

实验结果：

```
$ go test -test.bench="." ./labs04
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs04
Benchmark_Loop1-4        1538084               652 ns/op
Benchmark_Loop2-4        1449510               714 ns/op
Benchmark_Loop3-4        2020272               615 ns/op
Benchmark_Loop4-4          83190             15043 ns/op
PASS
ok      github.com/aptxx/go-labs/labs04 6.919s
```

结论：对结构体列表的range循环最消耗性能，因为数据要重复复制。