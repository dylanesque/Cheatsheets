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

- `components`: Vue components that are included in the template

- A Vue instance is a Vue component, the main difference being that the instance is mounted.

# Terms

- **Directive:** A directive is a token that given Vue special instructions about a DOM element.

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

# Components




