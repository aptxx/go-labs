测试几种链表遍历查找的性能差异。

实验结果：

```
$ go test -test.bench="." ./labs07
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs07
Benchmark_Loop1-4         300890              3759 ns/op
Benchmark_Loop2-4         264192              4525 ns/op
Benchmark_Loop3-4          78105             15086 ns/op
Benchmark_Loop4-4          14858             78409 ns/op
Benchmark_Loop5-4           3274            337501 ns/op
Benchmark_Loop6-4         245563              4829 ns/op
Benchmark_Loop7-4         204226              5509 ns/op
PASS
ok      github.com/aptxx/go-labs/labs07 9.315s
```

确认算法有效：

```
$ go test ./labs07 -v
=== RUN   Test_Loop4
--- PASS: Test_Loop4 (0.00s)
=== RUN   Test_Loop5
--- PASS: Test_Loop5 (0.00s)
=== RUN   Test_Loop6
--- PASS: Test_Loop6 (0.00s)
PASS
ok      github.com/aptxx/go-labs/labs07 0.005s
```

结论：有空做个查询表达式解析器吧。