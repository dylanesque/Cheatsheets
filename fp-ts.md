- `pf-ts` is a functional programming library for TypeScript

- `pipe()` takes x number of arguments (first is a value, the rest are functions with arity 1), and returns the product

- `flow()` is similar to `pipe()`, but the first argument must be a function (which may have an 
arity greater than 1).The primary use case for flow is to avoid anonymous callback functions, so 
you have clearer code without having to shadow a variable in the outer scope.

- Option is a container specifically for a value that could be something, OR null or undefined:
  
```javascript
type Option<A> = None | Some<A>
```

This wrapper has several advantages we can't get from nullish coalescing or optional chaining, see 
[Ryan Lee's blog post about this](https://rlee.dev/practical-guide-to-fp-ts-part-2)

- Either represents one value or another, typicall used for error handling.