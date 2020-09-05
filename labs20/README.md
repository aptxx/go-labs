测试Go调用C和C调用Go的效率差异。

测试结果：

```
$ go test -bench="." ./labs20
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs20
Benchmark_Go_Call_C-4           18249034                58.2 ns/op
Benchmark_C_Call_GO-4            8984389               131 ns/op
PASS
ok      github.com/aptxx/go-labs/labs20 2.457s
```