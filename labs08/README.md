同labs07，区别是用slice替代链表结构。

试验结果：

```
$ go test -test.bench="." ./labs08
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs08
Benchmark_Loop1-4        1434618               824 ns/op
Benchmark_Loop2-4         485623              2455 ns/op
Benchmark_Loop3-4          72522             15806 ns/op
Benchmark_Loop4-4          14260             83010 ns/op
Benchmark_Loop5-4           3870            310496 ns/op
Benchmark_Loop6-4         288788              4142 ns/op
PASS
ok      github.com/aptxx/go-labs/labs08 9.085s

$ go test -test.bench="." ./labs07
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs07
Benchmark_Loop1-4         306654              3784 ns/op
Benchmark_Loop2-4         266779              4486 ns/op
Benchmark_Loop3-4          78882             15145 ns/op
Benchmark_Loop4-4          15771             78603 ns/op
Benchmark_Loop5-4           3517            334050 ns/op
Benchmark_Loop6-4         246798              4870 ns/op
Benchmark_Loop7-4         211639              5667 ns/op
PASS
ok      github.com/aptxx/go-labs/labs07 9.525s
```

结论：简单循环slice明显更快，但是加入查询后， slice的优势就可以忽略不计了。
