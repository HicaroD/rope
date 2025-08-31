# Rope

An implementation of the Rope data structure, which is useful for storing large
arrays that are frequently mutated. The Rope is often used instead of a string
(array of characters), but can be used to replace any kind of array. This
implementation provides a Rope for arrays of bytes, but it should be easy to
modify it for other types of elements (this can be made generic in future
versions of Go).

**This repository is a fork of the original
[code](https://github.com/zyedidia/rope). Most of the code is the same, but
there are improvements to modernize the codebase with newer Go features,
especially related to slice operations, such as `slices.Insert`,
`slices.Concat` and more.**

## Benchmarkings

```
$ go test -bench=. -benchmem ./...
goos: linux
goarch: amd64
pkg: github.com/HicaroD/rope
cpu: AMD Ryzen 5 5600G with Radeon Graphics
BenchmarkConstruction/Size1000-12               44288283                25.39 ns/op           64 B/op          1 allocs/op
BenchmarkConstruction/Size10000-12              47274993                25.03 ns/op           64 B/op          1 allocs/op
BenchmarkConstruction/Size100000-12              3229021               377.8 ns/op           960 B/op         15 allocs/op
BenchmarkConstruction/Size1000000-12              327526              3290 ns/op            8128 B/op        127 allocs/op
BenchmarkConstruction/Size10000000-12              16694             76722 ns/op          131008 B/op       2047 allocs/op
BenchmarkSplice/Size1000:Splice10-12            28632072                40.35 ns/op            0 B/op          0 allocs/op
BenchmarkSplice/Size10000:Splice10-12           11442072               101.2 ns/op             0 B/op          0 allocs/op
BenchmarkSplice/Size100000:Splice10-12           6716014               178.7 ns/op             0 B/op          0 allocs/op
BenchmarkSplice/Size1000000:Splice10-12          4181577               287.5 ns/op             0 B/op          0 allocs/op
BenchmarkSplice/Size10000000:Splice10-12         2501566               466.2 ns/op             3 B/op          0 allocs/op
BenchmarkSpliceString/Size1000:Splice10-12              34040806                34.71 ns/op            0 B/op          0 allocs/op
BenchmarkSpliceString/Size10000:Splice10-12             12070054                97.25 ns/op            0 B/op          0 allocs/op
BenchmarkSpliceString/Size100000:Splice10-12             1000000              1038 ns/op               0 B/op          0 allocs/op
BenchmarkSpliceString/Size1000000:Splice10-12              91444             14156 ns/op               0 B/op          0 allocs/op
BenchmarkSpliceString/Size10000000:Splice10-12               856           1302053 ns/op               0 B/op          0 allocs/op
PASS
ok      github.com/HicaroD/rope 17.925s
```

## License

This project is licensed under the MIT license. See the original author's
license [here](./LICENSE).
