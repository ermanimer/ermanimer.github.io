# Detecting Shadowed Variables

You can install and run shadow linter to detect shadowed variables.

**Code:**

```go
package main

import "fmt"

func main() {
    x := 10
    if x > 5 {
        fmt.Println(x)
        x := 5
        fmt.Println(x)
    }
    fmt.Println(x)
}
```

**Output:**

```
10
5
10
```

**Install shadow linter:**

```bash
go install golang.org/x/tools/go/analysis/passes/shadow/cmd/shadow@latest
```

**Run shadow linter:**

```bash
shadow ./...
```

**Output:**

```
.../main.go:9:3: declaration of "x" shadows declaration at line 6
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Detecting Shadowed Variables](#detecting-shadowed-variables)
