测试值传参和指针传参的效率。

实验结果：

```
$ go test -test.bench="." ./labs02
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs02
Benchmark_Invoke1-4     1000000000               0.282 ns/op
Benchmark_Invoke2-4     1000000000               0.555 ns/op
PASS
ok      github.com/aptxx/go-labs/labs02 0.936s
```

结论：指针传参比值传参效率高一倍。