# To Learn a Language:

1) Learn the terms
2) Learn what data types are supported
3) What actions are supported
4) Best practices for that language

# Fundamental Python Data Types and Variables

- Wrapping an evaluation in `type()` will tell you what sort of data type is

- Numbers: int, float, bool

- Strings: str
  
- None is comparable to null in other languages

- Dictionaries are like objects in JS or hash tables in other programming languages

- Dictionary keys are immutable

- When iterating over dictionaries, knowing about items, keys, and values are important

- Lists are arrays

- A tuple is an immutable list; They are slightly more performant, so it's a good idea to use them in 
  cases of arrays that don't need to be mutated.

- A set is an 'unordered collection of unique objects', that is, no single value can be duplicated in a set



-"Don't read the dictionary"

- Variables in Python are snake-case

- Constants in Python are flagged by the use of upper-case caps

- Double-underscores indicate a var that is not to be mutated

- Triple-quotes allow multiline strings

- Types are converted by wrapping the value in the name of the type you need it converted to

# General notes

- When indentation is required, like in conditional statements, 2 spaces is the norm

# Functions 

- the `*args` and `**kwargs` arguments allow you to respectively input multiple arguments and keyword arguments

- Allowed order is params, *args, default parameters, **kwargs

# Scope

- Scope order is: local, parent's local, Global, built-in python functions

- When using global variables inside block scope, you need to flag them with the `global` keyword, OR pass them into functions, etc, via arguments




