# Order Of defer

You can defer multiple closures in a Go function. They run in last-in-first-out order; the last defer registered runs first.

**Code:**

```go
defer fmt.Println(0)
defer fmt.Println(1)
```

**Output:**

```
1
0
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Order Of defer](#order-of-defer)
