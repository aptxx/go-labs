测试interface{}类型转换判断和布尔值判断效率差异。

测试结果：

```
$ go test -bench="." ./labs23
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs23
Benchmark_UseInterface1-4       557644916                2.14 ns/op
Benchmark_UseInterface2-4       346172085                3.38 ns/op
Benchmark_UseBoolean-4          1000000000               0.562 ns/op
PASS
ok      github.com/aptxx/go-labs/labs23 3.567s
```
