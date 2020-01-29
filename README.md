# go-change-ref

## What is this?

`go-change-ref` change references to specific Go symbols (Type, Function, Variable...) in your project to another.

This tool will help you with refactoring your project when you want to move a definition to another package.

## Install

```
$ go install github.com/matope/go-change-ref
```

## How to use

### Before

```go
package main

import (
	"fmt"

	"github.com/matope/go-change-ref/example/pkg2"
)

func main() {
	var t2 pkg2.T2
	fmt.Println(t2)
}
```

### Run
```
$ go-change-ref -w \
    -from github.com/matope/go-change-ref/example/pkg2.T2 \
    -to   github.com/matope/go-change-ref/example/pkg3.T3 \
    ./...
```

### After

```go
package main

import (
	"fmt"

	"github.com/matope/go-change-ref/example/pkg3"
)

func main() {
	var t2 pkg3.T3
	fmt.Println(t2)
}
```
