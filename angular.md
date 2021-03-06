
# Components

- Components should do two things: 
  1) Consume only the data needed to satisfy and render it's template
  2) Capture events from the user and push that further up the stream to the "logic layer"

https://www.maestralsolutions.com/angular-application-state-management-you-do-not-need-external-data-stores/

-`<ng-content>` is a tag that takes the elements specified in a parent template and renders it when the in the specified place in a parent template
-With this technique, you can also use a technique called a projection slot, which works like an HTML attribute. 
`<ng-content select="h3"></ng-content>` can take an element, class, component names, etc.


`@ContentChild` is a decorator that binds to a reference of a component or element, allowing up to perform actions on changes to that component\

-How to hide elements that contain nothing:

// HTML
<div class="btn btn-primary"></div>

// CSS 
.btn.btn-primary:empty {
    display: none;
}


# Production-Grade Angular

Generally speaking:

- Your routing table will describe your features

- A feature will generally get a route...

- ...that route will generally navigate to a container component...

- ...and everything inside that container component will be a presentational component.

- Container components should satisfy inputs using the async pipe

- Components should be oblivious to:
  1) business logic 
  2) server communication
  3) application state

- Facades are for delegation only

- Server communication and state management should be decoupled

# Routing

- When reading route parameters, use snapshot for simple cases, like when you want to read those params only one. If it's much much complicated than that or is expected to change, use Observables.













 
