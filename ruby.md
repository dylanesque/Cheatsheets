# General

- Tabs are 2 spaces when writing Ruby

- Data types are first-class citizens in Ruby, like in JavaScript

- We can print on the screen with `puts`

# Primitive Data Types

- String interpolation in Ruby requires the use of double quotes.

```ruby
"I am #{first_name}"
```

- Symbols are often used as hash keys; Start them with a letter.

- In number operations, combining an int and a float will return a float

# Objects

- Putting a question mark at the end of a method indicates a boolean
  return value:

```ruby
"foobar".empty?
```

# Arrays

- Calling an array method with the bang operator at the end will allow that array to be mutated.

- The shovel operator `<<` can append items to the end of an array.

- The `to_a` method converts a range into an array

# Blocks

- Blocks are closures with which are often used to perform operations on a list or range of values.

# Methods

- Ruby methods have an implicit return, meaning that they return the last statement that's evaluated is a return isn't explicitly declared.

- Ruby supports multiple returns, like Golang
