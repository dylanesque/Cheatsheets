# Basics

- Vue is an SPA framework like React or Angular: it updates only the DOM elements necessary when prompted.
  
- Vue is added to a webpage via an instance:

```javascript
var vm = new Vue({
  el: '#app',
  template: `
      <div>
        <h1>I am the template from the Vue instance!</h1>
      </div>
    `,
  data: {
      name: 'John',
      age: 26
    },
    methods: {
      incrementAge() {
            this.age++
        }
    }
})
```
- Vue needs to be imported via a `script` tag for the instance to work.

- There are a lot of properties that can be defined in a Vue instance, but the most important are:

- `el`: An element for the Vue instance to control, where the app begins. 

- The Vue app can also be mounted via appending the call to the Vue instance ala: 
```javascript
new Vue({
    ...
}).$mount('#app')
```

- This lets up defer the mounting of the instance until specifically prompted to do so by an event, etc.
  
- `template`: Code for the Vue instance to display, which is HTML

- `data`: The data store for the Vue app, variables live here

- Data variables are interpolated onto the screen via double brackets, like AngularJS.

- NEVER interpolate user-generated content

- Interpolation can contain JS expressions, but only one per bracket pair

- `methods`: Where we store helper functions or methods
 
- `computed`: like methods, but it caches values
  
- `components`: Vue components that are included in the template

- A Vue instance is a Vue component, the main difference being that the instance is mounted.

- Component files end in the `.vue` file extension, and contain <template>, <script>, and <style> tags.

- Data is passed from parent to child using a `props` syntax very similar to React's. 
  `<ToDo_List v-bind:items='itemList' >`

- Children components communicate with parents via emitted events


# Terms

- **Directive:** A directive is a token that given Vue special instructions about a DOM element.

- **Mixins:** A mixin is a JS object used to shared common functionality between similar components.

# Directives

- All directives are prefixed with `v-`, followed by the keyword that gives that directive it's specific instructions

- Some directives require additional arguments, as seen in this example: <a v-bind:href="url"> ... </a>

- Directive filters work much like in Angular, using the pipe operator to separate the value and filtering function/method.

- You can create custom directives, as seen below: 

```javascript
Vue.directive('nameofthedirective', {
   bind(element, binding, v_node) {
     // do something
   }
})
```

- Custom directives must be declared before the Vue instance is initialized

- Conditional rendering is handled via directives, `v-if`, `v-else`, etc.

- While `v-if` removes an element from the DOM, `v-show` merely toggles it's visibility. This directive doesn't work with the template wrapper.

- Iterating is done with the `v-for` directive. Like in Angular, mutiple "structural" directives don't play well together.

- To deal with conditionally rendered loops, first filter the list using the 'computed' property before passing it down to the template.

## Reactive Paradigm/DOM Updating

- Array methods that trigger DOM updates: push, pop, shift, unshift, splice, reverse, sort

- `Vue.set()` is a method that updates elements, which takes 3 arguments:
  
  1) The list to be updated
  2) The index of them item
  3) The new value

- Lists require a key, like in React, so as to not lose place



- the <template> wrapper is used to group elements together that get rendered (or don't) based on the same condition



# Components




