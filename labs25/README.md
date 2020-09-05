测试LockOSThread()对chan消息处理的影响，本来是希望通过LockOSThread()可以独占线程，避免chan通讯发生的调度开销，结果跟预期相反，由于调度算法没有改变，LockOSThread()的goroutine反而需要等待关联的线程空闲了才能被执行到，所以反而是变慢了。

测试结果：

```
$ go test -bench="." ./labs25
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs25
Benchmark_Normal-4               7345437               168 ns/op
Benchmark_LockThread-4            120886              8435 ns/op
PASS
ok      github.com/aptxx/go-labs/labs25 2.537s
```