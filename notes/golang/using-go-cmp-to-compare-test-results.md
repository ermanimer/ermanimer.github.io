# Using go-cmp To Compare Test Results

You can use Google's go-cmp to compare test results. go-cmp does the comparison and returns a detailed description of what does not match.

**Code:**

```go
package record

import "time"

type Record struct {
	ID        string
	CreatedAt time.Time
}

func NewRecord(id string) Record {
	return Record{
		ID:        id,
		CreatedAt: time.Now(),
	}
}
```

**Code:**

```go
package main

import (
	"testing"

	"github.com/google/go-cmp/cmp"
)

func TestCreateRecord(t *testing.T) {
	expectedID := "a"
	expectedResult := Record{
		ID: expectedID,
	}

	result := NewRecord(expectedID)
	if diff := cmp.Diff(expectedResult, result); diff != "" {
		t.Error(diff)
	}
}
```



**Output:**

```
=== RUN   TestCreateRecord
    main_test.go:17:   main.Record{
          	ID:        "a",
        - 	CreatedAt: s"0001-01-01 00:00:00 +0000 UTC",
        + 	CreatedAt: s"2022-07-22 19:13:07.449739 +0300 +03 m=+0.002731834",
          }

--- FAIL: TestCreateRecord (0.00s)
FAIL
FAIL	test	0.454s
FAIL
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Using go-cmp To Compare Test Results](#using-go-cmp-to-compare-test-results)
