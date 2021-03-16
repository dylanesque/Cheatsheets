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

## Margin Collapse

Margin collapse is when overlapping margins take up less space than their total sums.

- Only vertical margins collapse: however, this will flip if the `writing-mode` is switched. The most accurate way to view this is that only block-direction margins collapse.

- Only adjacent elements collapse: placing an `hr` between two elements, for example, would be enough to prevent this from happening.

- The largest margin will win out in a collapse, and dictate the space taken up.

- Nesting one of the elements in a container like a `div` will NOT prevent collapsing. For this to happen, there can be no elements in-between the parent and child, no height set on the parent, and no border or padding set on the relevant parent edge.

- Margins can collapse in the same direction, as with a parent and child.

- Negative margins can still collapse; In the case of positive and negative margins overlapping, they'll be added together, and that sum will be the computed margin.

For multiple (more than 2) overlapping margins of mixed positivity:

1) Find the largest positive margin
2) Find the largest negative margin
3) Add them together

"Margin is like putting glue on something before you’ve decided what to stick it to, or if it should be stuck to anything."


# Centering

- The auto margin technique for centering elements is still quite useful when you have a single element that you need centered, and making the parent element a Flexbox or Grid container would be overkill.
  
# Flow Layout

## Inline Elements

- Inline elements don't have a width or height.

- Inline elements have extra "magic space" because the browser regards them as typography. To fix this quirk with images, either set their display as `block` or set the `line-height` on the wrapping div to `0`

## Block-level Elements

- By default, block-level elements have dynamic sizing.

## Inline Block

- Be aware of, but don't worry too much about [space sensitivity](https://css-tricks.com/fighting-the-space-between-inline-block-elements)

- Disadvantages: Inline block doesn't line-wrap, 

## Replaced Elements

- Replaced elements (like img, video, or canvas tags) embed a foreign object. They mostly behave as inline elements, but they can affect block layout in some ways.

- Buttons behave almost, but not exactly, as replaced elements.

## Height

To normalize application height when trying to fill the viewport:

1) Put `height: 100%` on every element before your main one.
2) Put `min-height: 100%` on that wrapper, and don't try using percentage-based heights there.
   
-`vh` units are unformtunatly not a viable solution here, since they're based on the total **possible** height after taking scrolling into consideration on mobile devices.

## Width

- Width can be expressed either as a keyword that dictates it's behavior (like `auto`), or as a measurement like `percentage` or `px`.

- `min-content` lets us shrink the element as much as it's children will allow. 

- `max-content` is the opposite of the above, with no line-breaks whatsoever. This is perfect for situations like only wanting background-color immediately around the child text.

- the [`fit-content`](https://developer.mozilla.org/en-US/docs/Web/CSS/fit-content) rule lets block level elements fill available space. It's a happy medium between the above two rules.

# Gotchas

- Padding gotcha: when it comes to padding, percentages always refer to the element's width, even for the top and bottom.
  
# Never Do These Things

- Add `outline: none` to an element; this breaks keyboard a11y
  
# Positioning

## Static

- Every element has this as a default `position`

- Setting position to any value other than `static` grants us access to the `top`, `left`, `right`, and `bottom` properties.

## Absolute

- This sort of positioning pulls an element completely out of flow.

- A drawback of this strategy is that it can collapse parent elements.
- 
- Josh says: 
  > "When you place an absolute item without specifying top/left/right/bottom, it sits where it would otherwise sit in 
  > its in-flow position, but it's incorporeal, it doesn't take up any space."

- **Only non-static elements can constrain absolutely-positioned children.**

The system for containing absolutely positioned elements is like so:

1) The DOM tree is traversed back to the top, looking for the first non-static parent, If found, the absolute child will be anchored to that element.

2) If none exist, it'll be anchored to the "initial containing block", a box the size of the viewport at the top of the document.

## Relative

- This property makes elements **relative** to their natural position

1) Constrains certain children
2) Enables additional CSS properties

# Responsive Tips and Tricks

## Max Width Wrapper

- https://stackblitz.com/edit/max-width-wrapper-component

# Patterns 

To center using absolute positioning:

1)  `position: absolute`
2)  All 4 cardinal directions (top, left, bottom, right) set to `0px`
3)  `margin: auto`
4)  An explicit width and height

- When you have a single element that needs to break from the usual flow of it's sibling elements, consider using a wrapping container to impose the behavior you need in that particular instance.

  
# Units

- Favor `rem`s for typography.

- Pixels for box model properties

- Go with either pixels or percentages for width or height, depending on the needs of your application.

- Prefer hsl for colors.
  
