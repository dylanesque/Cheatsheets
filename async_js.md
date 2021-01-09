# Callbacks

- In Node.js, one runthrough of the event loop is a tick. When we pass a function to the `process.nextTick()`process
method, we're telling the engine to run that code on the next tick of the loop.

- There are three ways to deal with errors in node: 1) logging it with console.error(), 2) throwing the error, and 3)
passing up the chain by calling `next()` with the error as an argument.

- `try...catch` doesn't behave in a predictable manner with synchronous code

# Promises

- A promise is a placeholder for a future value, like the [Early Bird Certificate Program](http://theswca.com/images-toys/figuretoys/ebkit.html) for the first Star Wars figures.