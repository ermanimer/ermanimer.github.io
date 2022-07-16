# Returning Nil Custom Errors

Returning uninitialized instace of custom error will return a non-nil error.

**Code:**

```go
package main

import (
	"fmt"
)

func main() {
	err := generateCustomErr(false)
	fmt.Println(err == nil)
}

type CustomErr struct {
	Message string
}

func (ce CustomErr) Error() string {
	return ce.Message
}

func generateCustomErr(returnErr bool) error {
	var ce CustomErr
	if returnErr {
		ce = CustomErr{
			Message: "custom error",
		}
	}
	return ce
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
		ce := CustomErr{
			Message: "custom error",
		}
		return ce
	}
	return nil
}
```

Or you can declare the error variable as the type of `error`:

```go
func generateCustomErr(returnErr bool) error {
	var ce error
	if returnErr {
		ce = CustomErr{
			Message: "custom error",
		}
	}
	return ce
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Returning Nil Custom Errors](#returning-nil-custom-errors)
