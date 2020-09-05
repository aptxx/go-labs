测试整数和浮点数的运算效率。

实验结果：

```
$ go test -test.bench="." ./labs05
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs05
Benchmark_IntAdd-4              1000000000               0.275 ns/op
Benchmark_Int8Add-4             1000000000               0.278 ns/op
Benchmark_Int16Add-4            1000000000               0.279 ns/op
Benchmark_Int32Add-4            1000000000               0.275 ns/op
Benchmark_Int64Add-4            1000000000               0.274 ns/op
Benchmark_Float32Add-4          1000000000               0.281 ns/op
Benchmark_Float64Add-4          1000000000               0.276 ns/op
Benchmark_IntSub-4              1000000000               0.275 ns/op
Benchmark_Int8Sub-4             1000000000               0.277 ns/op
Benchmark_Int16Sub-4            1000000000               0.277 ns/op
Benchmark_Int32Sub-4            1000000000               0.276 ns/op
Benchmark_Int64Sub-4            1000000000               0.275 ns/op
Benchmark_Float32Sub-4          1000000000               0.275 ns/op
Benchmark_Float64Sub-4          1000000000               0.277 ns/op
Benchmark_IntMul-4              1000000000               0.277 ns/op
Benchmark_Int8Mul-4             1000000000               0.275 ns/op
Benchmark_Int16Mul-4            1000000000               0.277 ns/op
Benchmark_Int32Mul-4            1000000000               0.278 ns/op
Benchmark_Int64Mul-4            1000000000               0.277 ns/op
Benchmark_Float32Mul-4          1000000000               0.279 ns/op
Benchmark_Float64Mul-4          1000000000               0.275 ns/op
Benchmark_IntDiv-4              1000000000               0.275 ns/op
Benchmark_Int8Div-4             1000000000               0.275 ns/op
Benchmark_Int16Div-4            1000000000               0.275 ns/op
Benchmark_Int32Div-4            1000000000               0.276 ns/op
Benchmark_Int64Div-4            1000000000               0.277 ns/op
Benchmark_Float32Div-4          1000000000               0.276 ns/op
Benchmark_Float64Div-4          1000000000               0.276 ns/op
PASS
ok      github.com/aptxx/go-labs/labs05 8.646s
```

结论：各类型运算速度相似。