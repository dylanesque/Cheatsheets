# General Strategies

- Before reaching for a class to target an element, first try to accomplish that with combinators, or descendant selectors.

- List of interitable properties: https://www.sitepoint.com/css-inheritance-introduction#list-css-properties-inherit

# Important resets/defaults

```css
*,
*:before,
*:after {
  box-sizing: border-box;
}
```

# Box Model Stuff

- When 3 values are provided for padding/margin/border, it takes the provided value for 'right' and plugs that into left.

- When border color isn't specified, it inherits the font-color for that element. This can be explicitly stated using the `currentColor` keyword for the color arg in statements.

- `outline-offset` allows you to add a gap between the element and the outline, like a second border.

# Centering

- The auto margin technique for centering elements is still quite useful when you have a single element that you need centered, and making the parent element a Flexbox or Grid container would be overkill.

# Gotchas

- Padding gotcha: when it comes to padding, percentages always refer to the element's width, even for the top and bottom.
  
# Never Do These Things

- Add `outline: none;` to an element; this breaks keyboard a11y

# Responsive Tips and Tricks

## Max Width Wrapper

- https://stackblitz.com/edit/max-width-wrapper-component

# Patterns 

- When you have a single element that needs to break from the usual flow of it's sibling elements, consider using a wrapping container to impose the behaviour you need in that particular instance.
  
# Units

- Favor `rem`s for typography.

- Pixels for box model properties

- Go with either pixels or percentages for width or height, depending on the needs of your application.

- Prefer hsl for colors.
  
