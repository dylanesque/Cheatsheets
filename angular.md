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


# Changes:









 
