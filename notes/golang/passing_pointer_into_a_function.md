# Passing Pointer Into A Function

When you pass a pointer into a function the pointer also will be copied while pointing the same address.

**Code:**

```go
package main

import "fmt"

func main() {
	i := 1
	pi := &i
	fmt.Printf("address of i: %p\n", pi)
	ppi := &pi
	fmt.Printf("address of pointer to i: %p\n", &ppi)
	print(pi)
}

func print(pi *int) {
	fmt.Printf("address of i: %p\n", pi)
	ppi := &pi
	fmt.Printf("address of pointer to i: %p\n", &ppi)
}
```

**Output:**

```
address of i: 0x1400012c008
address of pointer to i: 0x14000126028
address of i: 0x1400012c008
address of pointer to i: 0x14000126038
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Passing Pointer Into A Function](#passing-pointer-into-a-function)
