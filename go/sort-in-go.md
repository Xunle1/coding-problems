# Sort In Go

Use `sort` package to sort the arrays.

`sort` package has three built-in interface for three types.

```go
func main() {
    ints := []int{3,-1,2,5,0}
    floats := []float64{-2.3, -5.2, -3, 0, 2.1, 3.2}
    strings := []string{"Egg", "apple", "Hello", "world"}

    sort.Ints(ints)
    sort.Floats(floats)
    sort.Strings(strings)

    fmt.Println(ints)
    fmt.Println(floats)
    fmt.Println(strings)
    // [-1 0 2 3 5]
    // [-5.2 -3 -2.3 0 2.1 3.2]
    // [Egg Hello apple world]
}
```
