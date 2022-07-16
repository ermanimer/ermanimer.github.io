# Wrapping Errors with defer

You can wrap errors with defer using a named return parameter.

**Code:**

```go
package main

import (
	"errors"
	"fmt"
)

func main() {
	err := funcA()
	if err != nil {
		fmt.Printf("%+v\n", err)
	}
}

func funcA() (err error) {
	defer func() {
		if err != nil {
			err = fmt.Errorf("func a failed with, %w", err)
		}
	}()
	return errors.New("sample error")
}
```

**Output:**

```
func a failed with, sample error
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Wrapping Errors with defer](#wrapping-errors-with-defer)
