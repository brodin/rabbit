# rabbit

amqp connection setup for go apps

## Usage

```go
// Create
r := rabbit.New(
  rabbit.WithContext(ctx),
  rabbit.WithAuthority(uri),
  // More options available
)

// Start listening
msgs := r.StartListening()

// Handle messages
go func() {
  for {
    select {
      case <-ctx.Done():
        return
      case msg := <-msgs:
        // Handle message
    }
  }
}()
```
