# Intro To Flexbox

## What Is Flexbox
- Modern layout mode in **CSS3**
- **"flex"** is a value for the **display** property
- Replaces _floats_ and is much more elegant to work with
- Align items both horizontal (row) and vertical (column)
- Flex items can be re-ordered via CSS

### How it Works
- **display: flex;** /* Creates a "**flex container**" */
- All direct child elements are "**flex items**"

## Flex Basics
### Parent Element (Container)
The flex container becomes flexible by setting the display property to flex

- **flex-direction**: property defines in which direction the container wants to stack the flex items.
  - **column** value stacks the flex items vertically (from top to bottom)
  - **column-reverse** value stacks the flex items vertically (but from bottom to top)
  - **row** value stacks the flex items horizontally (from left to right)
  - **row-reverse** value stacks the flex items horizontally (but from right to left)
- **flex-wrap**: property specifies whether the flex items should wrap or not.
  - **wrap** value specifies that the flex items will wrap if necessary
  - **nowrap** value specifies that the flex items will not wrap (this is default)
  - **wrap-reverse** value specifies that the flexible items will wrap if necessary, in reverse order
- **flex-flow** property is a shorthand property for setting both the **flex-direction** and **flex-wrap** properties.
  - `flex-flow: row wrap;`
- **justify-content**: property is used to align the flex items in the main axis (horizontally)
  - **center** value aligns the flex items at the center of the container
  - **flex-start** value aligns the flex items at the beginning of the container (this is default)
  - **flex-end** value aligns the flex items at the end of the container
  - **space-around** value displays the flex items with space before, between, and after the lines
  - **space-between** value displays the flex items with space between the lines
- **align-items**: property is used to align the flex items cross axis (vertically)
  - **center** value aligns the flex items in the middle of the container
  - **flex-start** value aligns the flex items at the top of the container
  - **flex-end** value aligns the flex items at the bottom of the container
  - **stretch** value stretches the flex items to fill the container (this is default)
  - **baseline** value aligns the flex items such as their baselines aligns
- **align-content**: property is used to align flex lines (extra space in cross axis)
  - **space-between** value displays the flex lines with equal space between them
  - **space-around** value displays the flex lines with space before, between, and after them
  - **stretch** value stretches the flex lines to take up the remaining space (this is default)
  - **center** value displays display the flex lines in the middle of the container
  - **flex-start** value displays the flex lines at the start of the container
  - **flex-end** value displays the flex lines at the end of the container

### Child Elements (Items)
The direct child elements of a flex container automatically becomes flexible (flex) items.

- **order** property specifies the order of the flex items and value must be a _number_, default value is **0**.
- **flex-grow** property specifies how much a flex item will grow relative to the rest of the flex items and value must be a _number_, default value is **0**.
- **flex-shrink** property specifies how much a flex item will shrink relative to the rest of the flex items and value must be a _number_, default value is **1**.
- **flex-basis** property specifies the initial length of a flex item.
- **flex** property is a shorthand property for the **flex-grow**, **flex-shrink**, and **flex-basis** properties.
- **align-self** property specifies the alignment for the selected item inside the flexible container and it overrides the default alignment set by the container's **align-items** property.