- `pf-ts` is a functional programming library for TypeScript

- `pipe()` takes x number of arguments (first is a value, the rest are functions with arity 1), and returns the product:

```javascript
function toString(num: number): string {
  return `${num}`
}

pipe(1, add1, multiply2, toString) // '4'
```

- `flow()` is similar to `pipe()`, but the first argument must be a function (which may have an 
arity greater than 1).The primary use case for flow is to avoid anonymous callback functions, so 
you have clearer code without having to shadow a variable in the outer scope:

```javascript
import { flow } from 'fp-ts/lib/function'

pipe(1, flow(add1, multiply2, toString))
flow(add1, multiply2, toString)(1) // this is equivalent
```

# Data Types

- NonEmptyArray is an array guaranteed to have at least one item

## Option

- Option is a container specifically for a value that could be something, OR null or undefined:
  
```javascript
type Option<A> = None | Some<A>
```

- This wrapper has several advantages we can't get from nullish coalescing or optional chaining, see 
[Ryan Lee's blog post about this](https://rlee.dev/practical-guide-to-fp-ts-part-2)

## Option Methods

- Map Maps one value onto another:

```javascript
pipe(
  foo,
  O.fromNullable,
  O.map(({ bar }) => bar),
) // { _tag: 'Some', value: 'hello' }
pipe(
  undefined,
  O.fromNullable,
  O.map(({ bar }) => bar),
) // { _tag: 'None' }
```

- Flatten combines nested options.....

- Chain (often called flatMap in other functional paradigms) combines Map and Flatten

## Either 

- Either represents one value or another, typically used for error handling.

## Task

- Task is a function that returns a Promise that is expected to never fail.

- We avoid 'failure' by a combination of handling errors and making it impossible for 
invalid preconditions to be passed into a function.

- We can use the `of()` constructor to turn any value into a Task:

```javascript
import * as T from 'fp-ts/lib/Task'

const foo = 'boooo' // string
const bar = T.of(foo) // T.Task<string>

// Same As
const fdsa: T.Task<string> = () => Promise.resolve(foo)
```


## TaskEither

```javascript
interface Task<A> {
  (): Promise<A>
}
```

Ryan says:

> Functions commonly fail because of invalid preconditions. Take the function below, where the precondition is the length of id must be less than or equal to 36.

- TaskEither represents an async action that **can** fail

## Importing data types

- Favor an aliased import of the module in question to adhere to convention and for readability:

```javascript
import * as O from "fp-ts/lib/Option";
```

