测试类型判断和类型转换的效率。

执行结果：

```
$ go test -test.bench=".*" ./labs01
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs01
Benchmark_TypeSwitch-4          70865862                16.8 ns/op
Benchmark_NormalSwitch-4        808787748                1.48 ns/op
Benchmark_InterfaceSwitch-4     140373664                8.52 ns/op
PASS
ok      github.com/aptxx/go-labs/labs01 4.635s
```

结论：类型判断和类型转换这两个操作都比直接操作多几倍的消耗。

