测试不同压缩算法压缩json数据的压缩比和压缩效率。

实验结果：

```
$ go test -v ./labs29
=== RUN   Test_ByteSize
    labs29_test.go:64: 2 MB
--- PASS: Test_ByteSize (0.00s)
=== RUN   Test_Normal
--- PASS: Test_Normal (0.09s)
=== RUN   Test_Gzip_Level1
--- PASS: Test_Gzip_Level1 (0.08s)
=== RUN   Test_Gzip_Level5
--- PASS: Test_Gzip_Level5 (0.09s)
=== RUN   Test_Gzip_Level9
--- PASS: Test_Gzip_Level9 (0.09s)
=== RUN   Test_Snappy
--- PASS: Test_Snappy (0.09s)
=== RUN   Test_Normal_10S
    labs29_test.go:173: 52 MB/S
--- PASS: Test_Normal_10S (10.00s)
=== RUN   Test_Gzip_10S_Level1
    labs29_test.go:191: 47 MB/S
--- PASS: Test_Gzip_10S_Level1 (10.00s)
=== RUN   Test_Gzip_10S_Level5
    labs29_test.go:209: 43 MB/S
--- PASS: Test_Gzip_10S_Level5 (10.00s)
=== RUN   Test_Gzip_10S_Level9
    labs29_test.go:226: 42 MB/S
--- PASS: Test_Gzip_10S_Level9 (10.00s)
=== RUN   Test_Snappy2_10S
    labs29_test.go:242: 49 MB/S
--- PASS: Test_Snappy2_10S (10.00s)
PASS
ok      github.com/aptxx/go-labs/labs29 50.445s

$ ls -lah
total 4.6M
drwxrwxrwx 1 hank hank  512 Sep  5 12:44 .
drwxrwxrwx 1 hank hank  512 Sep  5 12:44 ..
-rwxrwxrwx 1 hank hank 1.7K Sep  4 22:30 README.md
-rwxrwxrwx 1 hank hank  48K Sep  5 12:44 json.gzip1
-rwxrwxrwx 1 hank hank  26K Sep  5 12:44 json.gzip5
-rwxrwxrwx 1 hank hank  19K Sep  5 12:44 json.gzip9
-rwxrwxrwx 1 hank hank 4.0M Sep  5 12:44 json.normal
-rwxrwxrwx 1 hank hank 401K Sep  5 12:44 json.snappy
-rwxrwxrwx 1 hank hank 4.5K Sep  5 12:44 labs29_test.go
```

实验结论：实验证明各种流压缩算法的吞吐量都高于json序列化过程，所以没必要用太高级压缩算法，可以用最高压缩比gzip