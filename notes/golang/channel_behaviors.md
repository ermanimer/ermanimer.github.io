# Channel Behaviors

|       | Unbuffered, Open | Unbuffered, Closed | Buffered, Open | Buffered, Closed | Nil |
|:------|:-----------------|:-------------------|:---------------|:-----------------|:----|
| Read  | Pauses until something is written | Returns zero value (use comma ok to see if closed) | Pauses if the buffer is empty | Returns a remaining value from the buffer. Returns zero value if the buffer is empty (use comma ok to see if closed) | Hangs forever |
| Write | Pauses until something is read | **Panics** | Pauses if the buffer is full | **Panics** | Hangs forever |
| Close | Works | **Panics** | Works | **Panics** | **Panics** |

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Channel Behaviors](#channel-behaviors)
