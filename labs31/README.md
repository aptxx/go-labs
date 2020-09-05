做内存池的时候有这样一个需求，给定一个数值，需要计算出这个数值落在2的第N次幂区间内，从而用这个N值索引出对应的池。

最直接的办法就是循环计算，因为2的20次幂就达到1M的大小了，这么大的内存块其实没有缓存的必要了，所以循环最多也就20次。

但是我很蛋疼了测试了sort包的Search函数，switch循环展开、if循环展开和人肉折半查找。

我电脑上测试结果如下：

```
$ go test -bench="." ./labs31
goos: linux
goarch: amd64
pkg: github.com/aptxx/go-labs/labs31
Benchmark_Normal-4      66063288                18.1 ns/op
Benchmark_Search-4      73216268                15.7 ns/op
Benchmark_Switch-4      229720687                5.04 ns/op
Benchmark_IF1-4         273368570                4.39 ns/op
Benchmark_IF2-4         543851665                2.20 ns/op
Benchmark_IF3-4         1000000000               0.273 ns/op
PASS
ok      github.com/aptxx/go-labs/labs31 7.533s
```

呵呵，蛋好疼。

补充：最后一个IF3测试是由群里的v1zze同学提供的算法，果然牛逼。