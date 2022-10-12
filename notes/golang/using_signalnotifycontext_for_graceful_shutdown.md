# Using signal.NotifyContext For Graceful Shutdown

You can use "signal.NotifyContext" method to create a child context that will be canceled when provided signals are received. This context cancellation should be handled in the process function as described in [Handling Context Cancellation And Timeout](notes/golang/handling-context-cancellation-and-timeout.md).

**Code:**

```go
package main

import (
	"context"
	"os/signal"
	"syscall"
)

func main() {
	ctx, cancelFunc := signal.NotifyContext(context.Background(), syscall.SIGINT, syscall.SIGTERM)
	defer cancelFunc()

	go func() {
		process(ctx)
	}()

	<-ctx.Done()
	
	// perform gracefull shutdown here
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Using signal.NotifyContext For Graceful Shutdown](#using-signalnotifycontext-for-graceful-shutdown)
