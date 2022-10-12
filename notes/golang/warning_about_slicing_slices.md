# Warning About Slicing Slices

When you slice a slice, the slice and the subslice share the same memory and changes to one are reflected in the other. Avoid modifying slices after they have been sliced or if they were produced by slicing.

**Code:**

```go
s1 := []int{0, 1, 2, 3}
s2 := s1[1:2]
fmt.Println("s1:", s1)
fmt.Println("s2:", s2)
s2[0] = 4
fmt.Println("s2:", s2)
fmt.Println("s1:", s1)
```

**Output:**

```
s1: [0 1 2 3]
s2: [1]
s2: [4]
s1: [0 4 2 3]
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Warning About Slicing Slices](#warning-about-slicing-slices)
