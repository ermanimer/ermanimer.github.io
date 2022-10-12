# Warning About For-Range Values

Each time the for-range loop iterates over a compound type, it copies the value from the compound type to the value variable. Modifying the value variable will not modify the value in the compound type.

**Code:**

```go
s := []int{0,1,2}
for _, v := range s {
    v += 1
}
fmt.Println(s)
```

**Output:**

```
[0 1 2]
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Warning About For-Range Values](#warning-about-for-range-values)
