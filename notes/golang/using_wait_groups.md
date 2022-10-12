# Using WaitGroups

You can process and wait FOR several goroutines by using a WaitGroup.

**Code:**

```go
func processABC() []int {
	result := make([]int, 0, 3)
	outChan := make(chan int, 3)
	var wg sync.WaitGroup
	wg.Add(3)
	go func() {
		defer wg.Done()

		outChan <- processA()
	}()
	go func() {
		defer wg.Done()

		outChan <- processB()
	}()
	go func() {
		defer wg.Done()

		outChan <- processC()
	}()
	go func() {
		wg.Wait()
		close(outChan)
	}()
	for out := range outChan {
		result = append(result, out)
	}
	return result
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Using WaitGroups](#using-waitgroups)
