# Handling Context Cancellation And Timeout

You can handle context cancellation and timeout by using context's done channel.

**Code:**

```go
func process(ctx context.Context, in int, processFunc func(int) (int, error)) (int, error) {
	var out int
	var err error
	doneChan := make(chan struct{})
	go func() {
		out, err = processFunc(in)
		close(doneChan)
	}()
	select {
	case <-doneChan:
		return out, err
	case <-ctx.Done():
		return out, ctx.Err()
	}
}
```

And you can use a data channel instead of the done channel.

**Code:**

```go
func process(ctx context.Context, in int, processFunc func(int) (int, error)) (int, error) {
	type data struct {
		out int
		err error
	}
	dataChan := make(chan data)
	defer close(dataChan)
	go func() {
		result, err := processFunc(in)
		dataChan <- data{result, err}
	}()
	select {
	case data := <-dataChan:
		return data.out, data.err
	case <-ctx.Done():
		return 0, ctx.Err()
	}
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Handling Context Cancellation And Timeout](#handling-context-cancellation-and-timeout)
