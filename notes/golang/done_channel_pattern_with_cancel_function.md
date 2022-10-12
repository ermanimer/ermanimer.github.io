# Done Channel Pattern With Cancel Function

You can provide a cancel function to close done channel.

**Code:**

```go
package main

import (
	"fmt"
)

func main() {
	outChan, cancelFunc := countTo(10)

	for out := range outChan {
		if out > 5 {
			break
		}
		fmt.Println(out)
	}
	cancelFunc()
}

func countTo(max int) (<-chan int, func()) {
	outChan := make(chan int)
	doneChan := make(chan struct{})
	cancelFunc := func() {
		close(doneChan)
	}
	go func() {
		for i := 0; i < max; i++ {
			select {
			case <-doneChan:
				return
			case outChan <- i:
			}
		}
		close(outChan)
	}()
	return outChan, cancelFunc
}
```

**Output:**

```
0
1
2
3
4
5
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Done Channel Pattern With Cancel Function](#done-channel-pattern-with-cancel-function)
