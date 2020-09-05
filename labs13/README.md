测试不同数据结构的对象数量差别。

测试存储结构体和存储对象的map类型占用的对象数量：

```
$ go run many_object1.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 10376
$ go run many_object2.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 10390
```

测试存储结构体和存储对象的slice类型占用的对象数量：

```
$ go run many_object3.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 161
$ go run many_object4.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 10165
```

未初始化的Slice和make后的Slice类型字段占用的对象数量：

```
$ go run many_object5.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 166
$ go run many_object6.go -gcflags '-N' | grep -o "HeapObjects.*"
HeapObjects = 15165
```

实验结论：

1. 存对象指针的map和存结构体的map，每条数据都占用一个对象数量，两种数据结构无差异
2. 存对象的slice和存结构体的slice有明显差异，存结构体的slice不重复占用对象数量
3. 未初始化的对象类型字段是不占用对象数量的
