# errors.Is And errors.As

Use errors.Is when you are looking for a specific instance (or a specific value). Use errors.As when you are looking for a specific type.

**Code:**

```go
package sentinelerr

type SentinelErr string

func (se SentinelErr) Error() string {
	return string(se)
}
```

```go
package main

import (
	"errors"
	"fmt"
)

var (
	ErrA = SentinelErr("a")
	ErrB = SentinelErr("b")
)

func main() {
	err := SentinelErr("a")
	fmt.Println(errors.Is(err, ErrA))
	fmt.Println(errors.Is(err, ErrB))
	var se SentinelErr
	fmt.Println(errors.As(err, &se))
}
```

**Output:**

```
true
false
true
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [errors.Is And errors.As](#errorsis-and-errorsas)
