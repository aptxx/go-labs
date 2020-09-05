测试binary.Write和硬编码的效率差异。

测试结果：

```
$ go test -bench="." ./labs24
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs24
Benchmark_UseBinaryWrite1-4     31254313                34.3 ns/op
Benchmark_UseBinaryWrite2-4      9977683               118 ns/op
Benchmark_UseHardcode-4         82606509                14.5 ns/op
PASS
ok      github.com/aptxx/go-labs/labs24 3.636s
```