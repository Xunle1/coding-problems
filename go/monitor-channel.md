# Monitor Channel

There are two ways to monitor channels in Go.

## for-range

`for-range` is used to monitor only one single channel.

```go
ticker := time.NewTicker(1 * time.Second)
for range ticker.C {
    fmt.Println("tick")
}
```

## for-select

`for-select` is used to monitor multiple channels.

```go
ticker := time.NewTicker(1 * time.Second)
for {
    select {
    case <-ticker.C:
        fmt.Println("tick")
    }
}
```
