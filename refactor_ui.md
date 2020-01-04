## Chapter One: Basics

+ Design a layout that supports the features of your site or application; don't fall
  in love with design ideas.

+ Don't over-design at first, leave room to improvise and refine later.

+ Choose a personality that fits the project, and keep that in mind.

+ Take advantage of creative limitations.

## Chapter Two: Hierarchy

+ Don't use font-size to exclusively communicate hierarchy: color and font-weight can work well.

+ #### Initial Planning Step You really only need two font-weights: heavy (600, 700), or normal (400, 500).

+ Sometimes emphasis comes from de-emphasizing related elements.

+ Try not to label (non-form) data unless you can't communicate what it is via context.

+ Also be on the lookout for headings that act as unnecessary labels.

+ Look for opportunities to solve contrast problems with weight, and vice-versa.

Action hierarchy:

+ Primary actions should be obvious, with high-contrast backgrounds.
+ Secondary actions should be clear, not prominent.
+ Tertiary actions should be discoverable, but not obtrusive.

## Chapter Three: Layout and Spacing

+ Start elements with WAY too much white-space, and subtract as needed.

+ Dense UIs have their place when there's a LOT of information to cover.

+ #### Initial Planning Step Define size scales ahead of time to prevent fiddly, ineffective tweaking
  of element size later on. (See page #63 of *Refactoring UI*)

  For example: 4px, 8px, 12px, 16px, 24px, 32px, 48px, 64px, 96px, 128px, 192px, 256px, 384px, 512px, 640px, 768px

+ Give an element the space it needs, and no more.

+ Try thinking in columns versus grids.

+ Relative sizing (like ems) doesn't scale well

+ Use spacing judiciously to better communicate relationships between elements.

## Chapter Four: Fonts

+ #### Initial Planning Step Establish a font scale early on (see page #91 of *Refactoring UI*)

For example: 12px, 14px, 16px, 18px, 20px, 24px, 30px, 36px, 48px, 60px, 72px

+ Don't use ems in your font scale; stick with rems or px.

+ #### Initial Planning Step Favor sans-serif for UI, and favor typefaces with at least five weights

+ Avoid condensed typefaces with short x-heights

+ To keep paragraph widths manageable, set a width of 20-35em.

+ If you have to have mixed font sizes on the same line, align by the baseline (bottom line)

+ Line-height should be proportional to paragraph width (see page # 106 from *Refactoring UI*)

+ Line-height and font-size should be inversely proportional: taller line-height for small text, etc.

+ Get creative about how a link is indicated, especially in UI with lots of links

+ Right-align numbers

+ If you have to use justified text, use hyphens

+ Letter spacing often doesn't need tweaking, but consider using it to tighten headlines, improve
  legibility with all caps.

## Chapter Five: Color

+ Favor HSL above other color formats

+ A strong color palette consists of greys, primary colors, and accent colors

+ #### Initial Planning Step First, pick a base color, one in the middle of your use spectrum. If it would look good as a button
  background, that's probably a good sign.

+ Next, pick the darkest and lightest shade you need to use. To do this, find colors that match the hue of
  your base color, and tweak saturation and lightness until you're happy.

+ Next, fill out the scale for that portion of the palette. 9 is a good number.

+ Generally, you'll need to adjust saturation as a color's lightness gets further away from 50%.

+ You can change a color's perceived brightness by rotating the hue.

+ Experiment with the temperature of your greys by adding some blue, ywllow, orange, etc, in the saturation.

+ If you have trouble meeting the contrast requirements for text, try flipping the text and background color scheme.

+ Use color to support the message, never as the sole means of communication.

## Chapter Six: Depth

+ Natural light comes from above; think about this when creating depth for elements.

+ To emulate height, use shadow length

+ Depth can be emulated with proper use of color

+ Overlapping elements is another useful technique for conveying depth

+ When overlapping images, separate them using an "invisible border" that's the same color as the background

## Chapter Seven: Images

+ Obviously, use high-quality images

+ Using an overlay on images with overlapping text ensures high contrast

+ Don't scale icons up or down, not even SVGs

+ Don't scale down screenshots

+ Make sure any user generated content is normalized in some way.

+ Inner box-shadow can prevent image "bleed" when the background colors are too similar.

## Chapter Eight: Misc

+ Find ways to improve default elements, like replacing list bullets with icons.

+ Accent borders are a nice way to punch up designs

+ For best gradient results, use two hues no more than 30 degrees apart.

+ Think about using repeating patterns in the background

+ Make sure empty states are displayed creatively.















