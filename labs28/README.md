测试`[]byte`转`string`的效率。

测试结果：

```
$ go test -bench="." ./labs28
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs28
Benchmark_Normal-4              263856129                4.51 ns/op
Benchmark_ByteString-4          1000000000               0.281 ns/op
PASS
ok      github.com/aptxx/go-labs/labs28 1.975s
```
