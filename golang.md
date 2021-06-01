# Overview

- Go (aka Golang) is a low-level language similar to C

- Improvements on C include [memory safety](), [garbage collection](), [structural typing](), and concurrency.

# Basics

- `&` turns a value into a pointer

- `*` turns a pointer into a value

- Variables of the same type can be declared on the same line: `var name, address string`

- A rune is a single text character
  
- Every primitive data type in Go has a `zero value`, which is the value that it's temporarily 
assigned if it's initialized but not assigned a value

- Go is a "pass by value" language, meaning that functions receive a copy of a value when it's passed as an argument to a parameter.
- This is why we sometimes utilize Pointers in Go

## Formatting Verbs

- `%f`: float
- `%d`: decimal integer
- `%s`: string
- `%t`: boolean
- `%v`: any value
- `%#v`: any value, formatted as it would appear in source code
- `%T`: Type of the supplied value
- `%%`: A literal percent sign

# Reference & Value in Go

- Value types (use pointers to change these in a function): int, float, string, bool, structs

- Reference types: slices, maps, channels, pointers, functions


## Commands

- The command `go run main.go` is how to run a package

- `go build` builds an exe

- `go format` formats all files in a directory

- `go install` installs packages

- `go run` runs a program

- `go fmt` manually formats a program

- `go version` prints the current version



## Looping

- The for loop is the main looping construct in Go

```golang
for i := 0; i++ {
    fmt.Println(i)
}
```

# Data Structures

- Arrays are statically sized in Go, and not used as often as slices

## Maps vs Structs

### Maps

- Reference type
- Generally used for collections of related properties
- All keys (and separately, all values), must be of the same type
- Keys are indexed, so they can be iterated over
- Don't need to know the keys at compile time

### Structs

- Value type
- Values can be of different types
- Keys can't be indexed
- different fields need to be known at compile time
- Generally used to represent a thing with lots of different properties
  

## Packages

- Go is generally comprised of packages, which come in one of two flavors:

1. Executables make files that we can run.
2. Reusables are helpers or utilities.

## Templates

