测试不修改runtime代码的情况下获取goid的效率。

测试结果:

```
$ go test -bench="." ./labs27
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs27
Benchmark_Goid-4          335473              3453 ns/op
PASS
ok      github.com/aptxx/go-labs/labs27 1.203s
```