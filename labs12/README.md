测试jemalloc和malloc在go程序中是否有性能差别。

实验结果：

```
$ go test -test.bench=".*" ./labs12
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs12
Benchmark_AllocAndFree-4         9089193               131 ns/op
Benchmark_JeAllocAndFree-4       8907132               139 ns/op
PASS
ok      github.com/aptxx/go-labs/labs12 2.723s
```

实验结论：非常相近