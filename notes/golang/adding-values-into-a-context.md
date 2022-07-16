# Adding Values Into A Context

You can put and get values into a context by using the context package's WithValue method and the context's Value method. It is a best practice to use a custom type constant key.

**Code:**

```go
type key int

const userKey key = 1

func ContextWithUser(ctx context.Context, u User) context.Context {
	return context.WithValue(ctx, userKey, u)
}

func UserFromContext(ctx context.Context) (User, error) {
	u, ok := ctx.Value(userKey).(User)
	if !ok {
		return User{}, ErrUserNotFound
	}
	return u, nil
}
```

<hr style="height:1px;">

[Notes](../../index.md#notes) / [Golang Notes](../../index.md#golang-notes) / [Adding Values Into A Context](#adding-values-into-a-context)
