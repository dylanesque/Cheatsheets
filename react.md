# Basics

- JavaScript can be used to generate HTML code via the DOM, and understanding this is the first stepping stone in understanding React and what it does. If you know how to completely generate HTML from JS using [Document API](https://developer.mozilla.org/en-US/docs/Web/API/Document) methods like `querySelectorAll()`, you're good to go here.

- The `React.createElement` API, the lowest-level version of React. That method takes an element type and params as an argument, and returns a React Element. It also spells out that it is React itself that creates these elements, and the ReactDOM library that renders those created elements to the DOM. The "children" prop is discussed as well, something seen frequently in Gatsby. React is using the browser API under the hood, but in a much more declarative manner. To sum it up, think of the main React library as being responsible for rendering elements via `React.createElement()`, and ReactDOM for rendering those elements to the DOM, like `rootElement.append()`

- JSX is syntactic sugar on top of the basic React API that resembles HTML or XML. What it is is basically named custom components, with optional "props" which work much like HTML attributes. It's also worth noting that standard HTML attributes work in JSX, though they may sometimes need some syntactic adjustment, as in the famous case of "class" needing to be labelled as "className" in React. To expand on this, a React component is at it's most basic level a JS function that returns some markup or other elements. 

- On importing React: https://epicreact.dev/importing-react-through-the-ages/

# Debugging

React Dev Tools offer several ways to make debugging react easier including:

- Filtering of components to make debugging of large applications faster.

- A `renderedBy` list for components that lets you sift through owners of that component faster.

- An `owners tree` list that shows all components that a component renders.

# State

- The best definition of props and state, from the React Native docs:

> "As a general rule, use props to configure a component when it renders. Use state to keep track of any component data that you expect to change over time."

- `propTypes` provide runtime validation for React props. While you could use this, it may be better to use TypeScript instead, as it covers a lot more bases in terms of static analysis, and catches them earlier to boot.

- Styling in React happens in one of two basic ways: a) Writing styles inline with the `style` prop, and b) Standard CSS applied with the `className` prop.

- Forms aren't too different in React than in other JS paradigms, this module discusses controlled components, and the possibility of using ref instead of getting the `event.target.value` (try not to do this)

- This module discusses arrays, commonly rendered in React by mapping over an array, and the importance of keys to uniquely identify each array entity.

# Core API

*Coming Soon!*

# React Hooks

- In general, Hooks are how modern React stores and modifies state.

## useState

- `React.useState` is the hook you'll probably use the most, for setting and maintaining basic state. It's commonly written in the form:

`const [yeet, setYeet] = React.useState('nothing');`

...and is updated by passing the requisite argument to the `setWhatever` function:

`setYeet('the Kardashians');`

- Updating via this set function versus variable assignment is important, since the set function triggers a re-render.

- `this.setState()` is an asynchronous method. What this means is that if duplicate calls are made in a function, only the last one will be called. Furthermore, updated data from a setState call might not be available until the next render. Per the React docs:

> 'React may batch multiple setState() calls into a single update for performance.'

- Using functions can circumvent the aforementioned effect

## Extensibility and Advanced Use Cases

- State can be set initially with a default value that is either hard-coded, or passed in as a prop. 

- One useful pattern surrounding lazy initialization is to check for an existing value before loading an initial value, like so:
`() => window.localStorage.getItem('name') || initialName`

- When you have state that depends on other pieces of state, make sure you're dealing with that by deriving state instead of syncing it, as discussed in [this article](https://kentcdodds.com/blog/dont-sync-state-derive-it)

## Lifting State

- When it comes to the question of 'where does state live?', the way to go is to keep it as close to where it's being used as possible, which is in the closest common parent when children share state.

## useRef

- The useRef hook is how React can get a reference to a particular DOM node. We want to avoid doing this whenever possible since it's imperative as opposed to declarative and not really the "React Way", but it is sometimes necessary.

## useEffect

`React.useEffect(() => { something}, []);`

- `useEffect` is the hook used for impure actions, typically being used where lifecycle methods would have been called
in older versions of React. The empty array shown in the example is an optional second argument. If it's called with an empty array, it will only run on mount and unmount. More frequently, it's filled with dependencies such as state to tell useEffect whether or not to re-render based on any one or more of the dependencies included in the array having been changed.

- Think of side-effects or impure actions in React as not just potentially mutable operations, but data that 
  comes from or goes to sources outside the React application.

- It accepts a callback function that will run after the DOM is updated

- There are some gotchas surrounding async/await and useEffect, see this [Stack Overflow thread](https://stackoverflow.com/questions/53332321/react-hook-warnings-for-async-function-in-useeffect-useeffect-function-must-ret). The short version is that useEffect isn't supposed to return anything other than the callback function, and async functions automatically returns a promise. Kent suggests something like this:

```javascript
React.useEffect(() => {
  async function effect() {
    const result = await doSomeAsyncThing()
    // do something with the result
  }
  effect()
})
```

..or better yet:

```javascript
React.useEffect(() => {
  doSomeAsyncThing().then(result => {
    // do something with the result
  })
})
```

- A close cousin to useEffect is `useLayoutEffect`: while they almost identical, useEffect will be what you need most of the time. According
to Kent C. Dodds: 

> "However, if your effect is mutating the DOM (via a DOM node ref) and the DOM mutation will change the appearance of  the DOM node between the time that it is rendered and your effect mutates it, then you don't want to use useEffect. You'll want to use useLayoutEffect. Otherwise the user could see a flicker when your DOM mutations take effect.  This is pretty much the only time you want to avoid useEffect and use useLayoutEffect instead."

## Custom Hooks 

- Custom Hooks are nothing more than regular hooks extracted into a custom function for reusability

- When returning items from custom hooks, there is a give and take with using arrays versus objects:

1) Use an array if you want to rename output or have multiple uses of the hook
2) Use an object if you want named properties, or don't want return order to matter

## Other Patterns covered in this chapter

- The below function takes reusability and extensibility to the next level with several techniques:

1) The key argument is a generic name for several possible arguments that could be passed in
2) There are default values for serialize and deserialize, which will work for most things we pass into or retrieve from localStorage,
   but allow for other types of conversion to be passed in
3) See comments on line #86
4) There is logic that accounts for a key that has changed

```javascript
function useLocalStorageState(
  key,
  defaultValue = '',
  {serialize = JSON.stringify, deserialize = JSON.parse} = {},
) {
  const [state, setState] = React.useState(() => {
    const valueInLocalStorage = window.localStorage.getItem(key)
    if (valueInLocalStorage) {
      return deserialize(valueInLocalStorage)
    }
    // The below logic accommodates a default value that is a function
    return typeof defaultValue === 'function' ? defaultValue() : defaultValue
  })

  // The logic surrounding prevKeyRef accounts for a changing key
  const prevKeyRef = React.useRef(key)

  React.useEffect(() => {
    const prevKey = prevKey.current
    if (prevKey !== key) {
      window.localStorage.removeItem(prevKey)
    }
    prevKeyRef.current = key
    window.localStorage.setItem(key, serialize(state))
  }, [key, serialize, state])

  return [state, setState]
}
```

## State Recipes

- Changing parent state from a child component, by https://stackoverflow.com/users/9418800/moshfiqrony, from https://stackoverflow.com/questions/35537229/how-can-i-update-the-parents-state-in-react:

```js
import React, {useState} from 'react';

const ParentComponent = () => {
  const[state, setState]=useState('');
  
  return(
    <ChildConmponent stateChanger={setState} />
  )
}


const ChildConmponent = ({stateChanger, ...rest}) => {
  return(
    <button onClick={() => stateChanger('New data')}></button>
  )
}
```

# Advanced React Hooks

- The `useReducer` hook's closest equivalent is the Redux framework: if you have state management needs that are far too complicated for useState to handle, you want to reach for this. useReducer contains a lot of the best parts of Redux, but is not entirely a drop-in replacement for it.

- `useCallback` exists to deal with the problem of a function being a dependency in the useEffect dependency array: 
Functions get re-initialized every render, which makes them brand new every render, so it will get called every render, regardless of whether or not that's the actual intention.

- It's structure is much like that of useEffect: The function in question is passed as an argument to the hook, then list the actual dependencies in the dependency array. If they're unchanged on future renders, REact will give the same function it did last time

- There are instances where you'll want to use a pattern that flags operations as unsafe or not to be performed if 
the component has been unmounted

- The `useContext` hook emulates the older Context API that exists for the problem of prop drilling.

-Kent says: 

> "Context also has the unique ability to be scoped to a specific section of the React component tree. A common mistake of context (and generally any “application” state) is to make it globally available anywhere in your application when it’s actually only needed to be available in a part of the app (like a single page). Keeping a context value scoped to the area that needs it most has improved performance and maintainability characteristics."

-`useImperativeHandle` is described in the React docs as:

> "useImperativeHandle customizes the instance value that is exposed to parent components when using ref. As always, imperative code using refs should be avoided in most cases. useImperativeHandle should be used with forwardRef"

- Uses of this hook should be fairly infrequent, and always documented as to why it's necessary in that particular case.

## React Component Lifecycle

1. Mount: Lazy initializers (functions passed to `useState` or `useEffect`) are run.

2. Update: The component is rendered, which consists of:
   - React updates the DOM
   - Performs cleanup of layoutEffects
   - Runs layoutEffects

Then:

- The browser paints the screen
- Performs cleanup of effects
- runs effects

- Updates are triggered by a parent re-render, or changes to state or context.


# Advanced React Patterns

## The Context Module pattern 

- This pattern is most useful when using useContext and useReducer together. If, in a situation like this, 
you find yourself making custom functions in the consuming component, or importing helper functions, then it may be a good idea to import those functions and the context provider from a separate module. In short, make sure you're providing everything you need to consume Context **with** that Context.

## Compound Components 

-This pattern can be thought of like ul and li or select and option: A parent and child relationship that you don't ever see used apart from each other. So we have something like:

```javascript
function Guitar({ children }) {
  const [pickupPosition, setPickupPosition] = React.useState('neck');
  const toggle = () => setPickupPosition(!on)
}
```

1) Mapping over the children of a parent and cloning the state and props into new children elements
2) Using a context provider and sharing state that way

When to use one or the other? 

- Map over children when you only have to worry about direct descendants
- Use context when you don't know how deep the tree needs to go

## Prop Collections and Getters

- The 'Prop Collections' pattern is basically what it sounds like: an object of props in a custom hook that get spread out and used in components.

- The limitations of this pattern are that is a default property in a prop collection needs to be overridden, this is hard to do without breaking other functionality.

- The 'Prop Getters' pattern an an extension of the above pattern that involves:

1) A function that that accepts and returns certain properties, and arbitrary props as arguments. For example:

```javascript
// Helper function that calls arbitrary number of functions:
function callAll(...fns) {
  return (...args) => {
    fns.forEach(fn => {
      fn && fn(...args)
    })
  }
}

// Prop getter function:
function getTogglerProps({ props, ...onClick } = {}) {
    return {
      'aria-pressed': on, onClick: callAll(onClick, toggle),
      ...props
    }
  }
```
 
## State Reducer

- The state reducer pattern involves using a reducer to allow users to add props/functionality to a component, rather than trying to code up every possible use case. 

- This can be done by providing a default reducer, but accepting a custom reducer as a possible argument

## Control Props

- Control props not only allow users to manage state changes in components, but control when they happen. The most visible example of this pattern are controlled form components.

# Epic React: React Performance

- Using dev tools like the Coverage, Performance, and Network tabs are a good way to ensure that performance changes
you're making actually change performance for the better

-When evaluating performance you REALLY want to do so in production mode to get the clearest idea of what your users would be experiencing, and to avoid premature/unnecessary optimization.

## Code Splitting

-Code Splitting is the practice of not loading module code until it's immediately needed, resulting in less code being fetched upon an initial load

-React.lazy relies on a Suspense fallback component: be mindful of exactly where you place that component, and who it impacts what gets loaded.

-A common way to achieve this is using the React.lazy API: https://reactjs.org/docs/code-splitting.html

-If some sort of user interaction indicates that some code will be needed soon, consider loading the necessary module
when the user mouses over a certain element, etc

-If you're using Webpack, you can set 'magic comments' to instruct the pre-fetching of code: https://webpack.js.org/api/module-methods/#magic-comments

## useMemo for Expensive Calculations

-The Problem: Expensive calculations will be performed with EVERY render of a component, whether or not in the inputs 
for those functions change.

-The `useMemo` hook will memoize expensive calculations, only re-running them on subsequent renders if it's specified dependencies have changed

-Web workers are another possible answer to performance issues: https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API/Using_web_workers

## React.memo for reducing re-renders

- The lifecycle of a React app:

render → reconciliation → commit
      ↖                   ↙
          state change

-Things that cause the re-rendering of a React component:

- It's props change
- It's internal state changes
- It is consuming context values which have changed
- It's parent re-renders

-`React.memo` (for function components) and/or `React.PureComponent` (for legacy class components) prevent a component
from re-rendering solely because it's parent re-rendered.

-React.memo also accepts a optional second argument in the form of a comparison function, though this can sometimes be circumvented by lifting state to above the componet, so React.memo checks it automatically.

## Window large lists with react-virtual

-Sometimes there's too much data, or too many components to load all at once. A strategy to deal with this is only load what's immediately need with libraries like `react-virtual`

## Optimizing context value

-When a provided value changes in context, it triggers a re-render of all consuming components, regardless of whetehr or not they're memoizing values, etc. The solution for this is to memoize values being passed into the context provider.

-The extra credit for this section involves Kent splitting context providers; this needs further study.

## Fix perf death by a thousand cuts

-The first example in this modules talks about examining global state, and colocating state that doesn't need to be there.

-Sometimes, separate context providers are the answer.

# Epic React: Testing React Apps

-When you need to mock data for tests, faker is a good option: https://www.npmjs.com/package/faker

## Simple Test with ReactDOM

-This chapter covers simple assertions and statement using Jest.

-The `dispatchEvent()` API models how things happen in the browser slightly more correctly:

```
const incrementClickEvent = new MouseEvent('click', {
  bubbles: true,
  cancelable: true,
  button: 0,
});
increment.dispatchEvent(incrementClickEvent);
```
-'bubbles' needs to be set to true here, to model event delegation/bubbling

## React Testing Library 

- Instead of hard-coding text elements, consider using snapshots to make your tests less brittle in the face of unexpected changes

## Avoid Implementation Details

- Kent says:

> "One of those is more clear than the other, but that's irrelevant to the point: The implementation of your abstractions does not matter to the users of your abstraction and if you want to have confidence that it continues to work through refactors then **neither should your tests.**"

- Using utilities like the 'screen' portion of react-testing-library can help make your tests short and more resilient 
to codebase modifications.

## Integration Testing

Kent tests:

- Rendering the entire application, including providers

- That the loading element is removed

- That the logged-in state is happening

- Rendering a book page

- That certain UI elements are present

- Mocks server using msw


# Epic React: React Suspense

## Simple Data-Fetching

## Render as you Fetch

-The intention of 'render as you fetch' is to get the data as soon as you have the information you need for the data.

## useTransition

-The `useTransition` hooks exists to improve loading state behavior. What it does is delay the typical React.Suspense 
fallback component from rendering so you can utilize other UI changes or behaviours.

## Caching Resources

-Caching requires a thoughtful approach in React, since the render 

## SuspenseImage



## SuspenseList 

-SuspenseList coordinates the order of suspended components

## Render-As-You-Fetch without Suspense

- Fetch resources as early as humanly possible

# Render Props

- Render props is defined by the React docs as:

> "The term “render prop” refers to a technique for sharing code between React components using a prop whose value is a function."

- While they have been largely replaced by custom hooks, there are still some corner cases where they are useful: https://kentcdodds.com/blog/react-hooks-whats-going-to-happen-to-render-props














