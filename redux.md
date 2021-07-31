# API

- `compose()` is a zero-point function that allows you to chain functions together

- `createStore()` takes a reducer as an argument and...creates the store.

## Reducers

- A reducer takes the current state and action, and updates the state accordingly.

Rules:

1. Don't mutate anything, replace something that needs to change.
2. You have to return SOMETHING.
3. Prefer flat objects.
4. It's just a function!



