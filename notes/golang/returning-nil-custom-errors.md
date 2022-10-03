# Returning Nil Custom Errors

Returning uninitialized instance of custom error will return a non-nil error.

**Code:**

```go
package main

import (
	"fmt"
	"strconv"
)

func main() {
	err := generateCustomErr(false)
	fmt.Println(err == nil)
}

type CustomErr struct {
	Code    int
	Message string
}

func (err *CustomErr) Error() string {
	return strconv.Itoa(err.Code) + " " + err.Message
}

func generateCustomErr(returnErr bool) error {
	var err *CustomErr
	if returnErr {
		err = &CustomErr{
			Code:    1,
			Message: "custom error",
		}
	}
	return err
}
```

**Output:**

```
false
```

The reason why err is non-nil is that error is an interface. For an interface to be considered nil, both the underlying type and the underlying value must be nil.

You can explicitly return nil for the error value:

```go
func generateCustomErr(returnErr bool) error {
	if returnErr {
		err := &CustomErr{
			Message: "custom error",
		}
		return err
	}
	return nil
}
```

Or you can declare the error variable as the type of error:

```go
func generateCustomErr(returnErr bool) error {
	var err error
	if returnErr {
		err = &CustomErr{
			Message: "custom error",
		}
	}
	return err
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Returning Nil Custom Errors](#returning-nil-custom-errors)
