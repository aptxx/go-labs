尝试优化一段代码。

测试结果：

```
$ go test -bench="." ./labs17
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs17
Benchmark_Method1-4        60812             20440 ns/op
Benchmark_Method2-4       274543              4484 ns/op
Benchmark_Method3-4       308395              3989 ns/op
Benchmark_Method4-4       315738              3855 ns/op
Benchmark_Method5-4       322383              3660 ns/op
PASS
ok      github.com/aptxx/go-labs/labs17 7.445s
```

还可以再继续优化初始时候的数值转字符串，数值转字符串也是比较大的消耗。