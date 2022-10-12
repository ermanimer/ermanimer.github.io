# Profiling Benchmark Tests With pprof

You can create cpu and memory profile outputs of a benchmark test.

**Code:**

```
go test -bench . -benchmem -memprofile mem.out -cpuprofile cpu.out
```

Your can run pprof with the created outputs.

**Code:**

```
go tool pprof -http :8080 cpu.out
go tool pprof -http :8081 mem.out
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Profiling Benchmark Tests With pprof](#profiling-benchmark-tests-with-pprof)
