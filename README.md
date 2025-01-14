# Unexpected Panic with Nil Map Access in Go

This repository demonstrates a common error in Go where accessing a map without checking if it's nil can lead to a runtime panic.  The `bug.go` file contains the erroneous code, while `bugSolution.go` shows the corrected version.

## Problem

In Go, attempting to access a key in a `nil` map will cause a `runtime panic`. This can be difficult to debug, especially in larger applications.

## Solution

The solution is to always check if the map is `nil` before attempting to access a key.  This can be done using the following pattern:

```go
if m != nil {
    // Access map safely
}
```

Alternatively, use the comma ok idiom for concise nil checks:

```go
value, ok := m["key"]
if ok {
    // Key exists
}
```