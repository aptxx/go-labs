测试对象创建的效率。

实验结果：

```
$ go test -test.bench="." ./labs03
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs03
Benchmark_NewStruct1-4          1000000000               0.275 ns/op
Benchmark_NewStruct2-4          1000000000               0.282 ns/op
Benchmark_NewStruct3-4          1000000000               0.279 ns/op
Benchmark_NewStruct4-4          1000000000               0.278 ns/op
Benchmark_NewStruct5-4          197175687                6.07 ns/op
PASS
ok      github.com/aptxx/go-labs/labs03 3.062s
```

结论：创建对象消耗相似，依次赋值会有较多开销。