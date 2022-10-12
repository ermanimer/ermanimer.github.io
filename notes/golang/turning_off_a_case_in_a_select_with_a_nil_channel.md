# Turning Off A Case In A Select With A Nil Channel

You can turn off a case in a select by setting the input channel to nil after checking if the input channel is closed by using the comma ok idiom.

**Code:**

```go
for {
	select {
	case in, ok := <-inChan1:
		if !ok { // inputChan1 is closed
			inChan1 = nil // this case will never succeed again
			continue
		}
	case in, ok := <-inChan2:
		if !ok { // inputChan2 is closed
			inChan2 = nil // this case will never succeed again
			continue
		}
	case <-doneChan:
		return
	}
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Turning Off A Case In A Select With A Nil Channel](#turning-off-a-case-in-a-select-with-a-nil-channel)
