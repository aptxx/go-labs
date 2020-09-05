测试缓存反射信息对效率的影响。

```
$ go test -bench="." ./labs19
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs19
Benchmark_________Verify-4       1674547               706 ns/op
Benchmark_____FastVerify-4      11271606               103 ns/op
Benchmark_VeryFastVerify-4      20655146                55.9 ns/op
PASS
ok      github.com/aptxx/go-labs/labs19 4.403s
```