测试平方根算法的效率。

测试结果：

```
$ go test --bench="." ./labs16
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs16
Benchmark_Method1-4      4155932               292 ns/op
Benchmark_Method2-4     1000000000               0.279 ns/op
Benchmark_Method3-4     1000000000               0.279 ns/op
PASS
ok      github.com/aptxx/go-labs/labs16 2.141s
```
