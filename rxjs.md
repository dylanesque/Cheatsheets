# Observables
- An Observable is something that emits events over time
- An observable needs to be not only created, but subscribed to.
- You can `.subscribe()`, and also `.unsubscribe()` from an observable.
- Observable are cold by default: What this means is that you need to manually subscribe to them to get data.

# Operators

- An Operator acts upon the events that an observable emits, transforming or checking the data in some way

## Creation Operators

- Creation operators streamline the creation of observables.

- `.fromEvent(element, 'event')` creates an observable from a DOM event

- `of()` is used to make observables out of static values
 
- `range()` takes a range of numbers and and fills in the blanks (range(1, 10))
 
- The `from()` operator creates an observable from nearly anything

- The `interval()` operator creates an observable that's timer-based
  
- The `timer()` operator allows for more fine-grained control over interval timing

- The `defer()` operator takes a function as an argument and executes it when an Observer subscribes to it.

## Pipeable Operators

- Pipeable operators transform the data that passes through them

- `.pipe()` needs to be added BEFORE a subscribe call

- `map` applies a given function to the data that passes through the pipe, much like the `.map()` Array method in JS

- `pluck()` is like map, "but meant only for picking one of the nested properties of every emitted object."

- `filter` also works much like the Array.prototype.filter() method

- And again, `reduce()` is like it's Array method counterpart

- `scan()` is a lot like reduce, except that it returns the value at each step of the way, instead of only once at the end.

- `shareReplay()` allows you to reduce the number of HTTP requests/API calls from a single source

## Combination Operators

- `forkJoin()` takes a number of observables, and emits the last emitted value from each when they are complete.

- `combineLatest()` allows you to subscribe to a combination of observables. Will not emit until each observable emits at least one value apiece.

- `zip()` waits until all observables in question emits, then returns those values to the observer.

## Filtering Operators

- `first()` only allows the first emitted value to go through. If this observable completes before a value is emitted, it throws an error.

- `last()` does the opposite of `first`

- `take(`) allows us to specify a number of values to return

- `skip()` allows us to bypass the first x values returned by an observable, also `skipUntil()`

- `takeWhile()` allows us to receive data until a certain condition is met

- `takeUntil()` takes another observable as an argument, and emits values until the other observable returns a value.

  - `takeUntil` can be used to automate unsubscription from long-running streams, as seen in [this example](https://rxjs-emjeza.stackblitz.io).

- `distinctUntilChanged()` ignores emitting values until they change from the last emitted value

## Multicasting Operators

- shareReplay() or share() is a handy way to keep the results of an HTTP request or API call in memory and use it in multiple places without making multiple calls

# Rate Limiting Operators

- `debounceTime()` "Discards emitted values that take less than the specified time between output"

- `throttleTime()` ignores values that happen during certain specified time windows

- `sample()` "Sample from source when provided observable emits"

# Transformation Operators

- concatMap vs mergeMap?

- `mergeMap(`) "Map to observable, emit values."

- `switchMap()` switches to a new observable when the value changes

- `concatMap()` queues all observables until released, "a single file line of operators". Is helpful when order of execution matters. Similar to switchMap, except that it won't subscribe to the next observable until the current one completes.

- `buffer()` buffers emitted values until the observable provided as an arg emits.

- `bufferCount()` buffers items up to the specified threshold, and then emits

- `bufferToggle()` captures events that happen between a specified threshold

# Observers
  
- An Observer (obviously) is what receives an observable, and has three callback functions: next (think Express.js next()), error, and complete. You can supply any, or none, of the callbacks.

- When we pass an argument to `next()`, we're basically say to put it in the pipeline

- An error will complete the stream it occurs in

-Best practice is to use the catchError operator to catch them

-Combining multiple streams via mergeMap or switchMap will keep the errored stream from closing

-the retry operator will retry an operation immediatetely

-the retryWhen() operator is a better bet when working with AJAX requests

# Subject

-A subject is both an observable and an observer, which is multicast

# Multicast vs Unicast

-Unicast observables emit a separate set of values for each observer that subscribes; All operators in a pipe
will be executed for each separate observer that subscribes

-This can easily lead to bad behavior!

-Multicast observables emit a single set of values for all observers that subscribe; All operators in a pipe are
executed only once

-Gotchas: The observable will be reset if it gets 'completed' or 'errored', then another subscriber is added. This will
also quickly run into issues with a later subscriber not seeing earlier events!

# Hot vs Cold

-A hot observable has a single event stream that's shared for all subscribers, old and new
-In a cold observable, the event stream is recreated for each new subscriber

# Schedulers

-Schedulers are time-based operations and operators

-Schedulers can be provided as optional arguments to observables, or with the .observeOn() operator

-asyncScheduler takes 3 arguments: work, delay, and state. This method is similar to setTimeout

-asyncSchedular vs delay?

-asapScheduler schedules work on the microtask queue, like Promise.resolve or queueMicrotask

# Tips and Tricks

- Use [`finalize()`](https://www.learnrxjs.io/learn-rxjs/operators/utility/finalize) to perform side-effects upon completion (or error).

- Whenever possible, extract commonly used/reused logic (such as retrying a failed request) into a function for improved resuability & code quality.

- Consider using combination operators to merge outside state into observable streams.





    