测试小数据量循环和map取数据以及硬编码取数据的性能消耗。

试验结果：

```
$ go test -test.bench="." ./labs06
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs06
Benchmark_Loop1-4       329194624                3.99 ns/op
Benchmark_Loop2-4       286965111                4.03 ns/op
Benchmark_Loop3-4       99019704                10.7 ns/op
Benchmark_Loop4-4       354465376                3.36 ns/op
Benchmark_Loop5-4       1000000000               0.276 ns/op
PASS
ok      github.com/aptxx/go-labs/labs06 6.192s
```

结论：硬编码 << for-range < for << map，map 小数据量尽量少用。
