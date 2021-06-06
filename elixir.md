-Elixir projects are created by running `mix new <PROJECT_NAME>` in the command line.

-`mix` also compiles the project, `mix run` runs the project

-`iex -S mix` starts IEX in the context of your project.

-The `.ex` extension is for files that are intended to be compiled into binaries, and `.exs` is for scripts that are to be run without compilation.

-Common Elixir style is two-space indentation and spaces, not tabs.

-Modules and functions in Elixir resemble blocks in Ruby with syntax like so:

```elixir
defmodule Amazing do
  # body of module
end

def rando_func() do
  # body of function
end
```

-The variable binding that happens in Elixir can ONLY happen on the left-hand side

-The LHS of variable assignment can't contain calculations or function calls.

-The underscore operator can do some special things related to pattern matching, including acting as a wildcard

[ a, _, _ ] # match a three element list (where each element is # potentially different to the others) and # associate the value of the first element with `a`

[ a, _, a ] # match a three element list where the first and # last elements are the same, binding that value to `a`

[ h | _ ] # extract just the head of a list

-Adding the pin operator (iex> ^life = 42) to variable assignment keeps that LHS from being reassigned

# Elixir Data Types

## Values

### Integers

-Integers can be written in decimal, hexadecimal, octal, and binary format
-Decimals MAY contain integers (1_000_000)

### Floats

-Your typical decimal

### Atoms

-An atom is a constant that represents the name of something, similar to symbols in Ruby

### Ranges

-A range of something written in the format of start...end, where start and end are integers

### Regular Expressions

-Your trusty old regular expression
`~r{regexp}`

## System Types

-System types are resources in the Erlang VM

### PIDs and ports

-A reference to a local or remote process, where a port is a reference to a (usually external) resource that
you'll be reading from or writing to

-The PID of the current process can be seen by calling `self`

## Collection Types

### Tuples

-An ordered collection, can contain mixed values. Immutable once created.

`{ :ok, 42, "next" }`

-Tuples typically have 2-4 elements, and collections with more items should probably be built with maps or structs

### Lists

-Lists in Elixir are linked lists. They may be empty, or have both a head and a tail. The head contains a value, and the tail is a list.

-Also immutable.

List concatentation: `[1,2,3] ++ [4,5,6]`

Diffing lists: `[1,2,3,4] -- [2,4]`

Checking for memebership: `1 in [1,2,3,4]`

Lists written as key-value pairs get converted to collections of tuples:

[ name: 'Mike', city: 'Boston', likes: 'Programming']

becomes:

[ {:name, 'Mike'}, {:city, 'Boston'}, {:likes 'Programming'} ]

### Maps

-A map is a collection of key-value pairs

guitars = %{ "G" => "Gibson", "F" => "Fender", "J" => "Jackson" }

-The main difference between maps and lists in Elixir is that maps only allow one entry per distinct key, where lists can repeat keys.

-Lists: Good for passing around options or command-line parameters
-Maps: Used for associative arrays

-Data is extracted from maps using the square bracket syntax:

```
guitars["G"]
"Gibson"
```

-If the key is an atom, dot notation can be used:
guitars.f
"Fender"

### Binaries

-Binaries are data in bit or byte forms, not likely to be used directly.

### Booleans, Operations & Comparison

-Elixir has three boolean values: true, false, and nil. nil is treated as false in boolean operations

-Comparison in Elixir follows this hierarchy:

number < atom < reference < function < port < pid < tuple < map < list < binary 

-Elixir has or, and, and not as boolean operators

-Elixir has standard mathematical operations, with two exceptions:

  -div yields a floating point result: div(a, b)

  -rem stands for remainder, think of it as the modulo operator of this language


#### Join operators

Concatentation:

binary1 <> binary2

list1 ++ list2

diff: 

list1 -- list2

(The above code removes elements of list2 from list1)

a in enum (Checks for inclusion)

### Variables and Scope

-Variable are lexically scoped in Elixir, usually inside blocks

### 'with'

The with operator:

  -Defines a local scope for variables

  -Gives some control over pattern-matching failures

## Functions

Anonymous functions are created via:

fn
 body
end 

We can also do arrow function style syntax/assignment:

`sum = fn (a, b) -> a + b end`
`sum.(1,2) = 3`

As in many languages, the signature parentheses are necessary, even if the function takes no arguments:




