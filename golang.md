# Overview

- Go (aka Golang) is a low-level language similar to C

- Improvements on C include [memory safety](), [garbage collection](), [structural typing](), and concurrency.

- Go is object-oriented, but much more weakly so than a language like Java

Recommended project structure:

- src folder for source code
- pkg for packages
- bin for executables

# Basics

- `&` creates a pointer to something in memory

- `*` gets a value from a pointer

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

## Reference & Value in Go

- Value types (use pointers to change these in a function): int, float, string, bool, structs

- Reference types: slices, maps, channels, pointers, functions

## Types

### Conversion

- 🔥 tip: Before you convert types, make sure that you're not passing them into a method that needs them to be a certain type, saving you the trouble of that conversion to begin with. A canonical example is `float64` being passed into `math.Round`.

# Commands

- The command `go run main.go` is how to run a package

- `go build` builds an exe

- `go fmt` formats all files in a directory

- `go install` installs packages

- `go run` runs a program

- `go version` prints the current version

- `go doc <somefunction>` prints out information about that method 

# Functions & Methods

- Unlike many other methods, there's a syntactical difference in how methods 
are written vs functions, namely that they take receiver parameters:

```go
func (s string) destroyString() {
    // something something string
}
```

- Functions are first-class, and can be declared as vars:


# I/O

- To read from stdin: `  reader := bufio.NewReader(os.Stdin)`
  
- To assign that to a string: `name, _ := reader.ReadString('\n')`
  
# Looping

- The for loop is the main looping construct in Go

```golang
for i := 0; i++ {
    fmt.Println(i)
}
```

# Concurrency 

- The order of execution between concurrent tasks is not known.

- goroutines are functions that are to be executed asynchronously.

- Channels are designed to synchronize goroutines.

## WaitGroups 

- WaitGroups wait for collections of goroutines to finish.

- The `Add` method 

# Data Structures

- Arrays are statically sized in Go, and not used as often as slices

## Maps vs Structs

### Maps

- The hash table implementation in Golang
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

# Web Development using Go

## Templates

- Templates let us create web pages with Go

- At a high level, we parse files (using `template.ParseFiles` or `template.ParseGlob`), and then execute them into a template.

- Functions can be mapped over using the `FuncMap` method from the template library...

- ...which can be passed into the `Funcs` method.



