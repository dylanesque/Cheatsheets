# Overview

- Go (aka Golang) is a low-level language similar to C

- Improvements on C include [memory safety](), [garbage collection](), [structural typing](), and concurrency.

# Basics

- `&` turns a value into a pointer

- `*` turns a pointer into a value

## Reference & Value in Go

- Value types (use pointers to change these in a function): int, float, string, bool, structs

- Reference types: slices, maps, channels, pointers, functions


## Commands

- The command `go run main.go` is how to run a package

- `go build` builds an exe

- `go format` formats all files in a directory

- `go install` installs packages

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

