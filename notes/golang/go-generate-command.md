# go generate Command

go generate scans special comments in the code and identifies commands to run.

**Code:**

main.go

```go
package main

//go:generate go run gen/gen.go

import (
	"fmt"
	"os"
)

func main() {

}
```

gen/gen.go

```go
package main

import (
	"fmt"
	"os"
)

func main() {
	if err := generateSampleFile(); err != nil {
		fmt.Println(err.Error())
	}
}

func generateSampleFile() error {
	f, err := os.Create("sample_file")
	if err != nil {
		return fmt.Errorf("creating sample file failed, %w", err)
	}

	f.WriteString("sample text")

	return f.Close()
}
```

**Generate:**

```
go generate
```

Or

```
go generate ./...
```

**Print Generated File:**

```
cat sample_file
```

**Output:**

```
sample text
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [go generate Command](#go-generate-command)