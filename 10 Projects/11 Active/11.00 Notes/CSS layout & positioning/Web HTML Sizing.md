---
zettel:
  - Fleeting Note
topic:
  - "[[Webdesign]]"
references:
  - "[[12.01 CSS layout & positioning]]"
created: 2024-09-01
status:
  - To Do
type: "[[Card]]"
tags: 
---

Do not size (in any unit) on an element itself (eg. an image) but rather on a class.

## Auto size

By default all web elements size is determined by the size of the content inside it. If you increase font size of a Heading element the element size increases and pushes other elements bellow downside.

It is recommended in the CSS layout & positioning that for sections we should have auto widht and heights and if needed, adjust just min H/W or max H/W. This will prevent elements overflow (eg. when the viewport height is lowered).

## Overflow

If there is an element with width and height set but the content (text) is too long, the text will overflow the size of the element.

We can disable the overflow, so the text ends at the edge of the element or we can make the element scrollable.

We can set the value to auto which makes element scrollable if there is enough space for it. If not it does not show the scrollbar.

## Fit

If we put an image inside the div, the div as a parent and its (auto) height and width are the same as image size. To display the image correctly we must (in webflow) do these steps:

1. Set fixed size of the parent div
2. Set 100% width and 100% height of the child image inside the div
3. Adjust the Fit properties:
    - fill
    - contain
    - cover (we want to set anchor point here)
    - none
    - scale down

## Web Size Units (will be a separate note)

### Pixels (px)

Absolute width and height.

Default in webflow.

Do not set too many explicit widths. Let content flow on smaller devices.

All other units are also known as relative units.

### Percentages (%)

Percentage of size of a parent element.

Eg width 25% means that elements always takes 25% of AVAILABLE space inside a parent element.

### Ems & rems (ems, rem)

em and rem are relative to the font size of the parent element and the root element, respectively.

We can use em to ensure the padding stays the same when increasing the font size.

The em unit means "my parent element's font-size"

The rem unit means "The root element's font-size" (rem stands for "root em"). Default font size of a browser.

### Viewport-based (vw, vh, vmin, vmax)

Represents the percentage of the viewport.

vh is viewport height

vw is viewport width

With vmin we are basing things off whichever viewport dimension (width or height) is smaller.

If viewport height is 100px nad viewport width is 50px than setting an element width 50vmin means its width will be 50% of the smaller viewport dimension which is width (50px < 100px height), thus the width will be 25px.

vmax bases things of larger dimensions.

In our case 50vmax would be 50px.

### Fractional (fr)

Thes units work only inside a grid.

If there are 4 columns than 1fr = 1/4. 5 columns means 1fr = 1/5.

If we change a fractional unit for one column, the rest columns will scale automatically to keep the ratio. The nominator and the denominator and all the math in between is automatically calculated.

Also the column gaps are caluculated accordingly.

### Character-based (ch)

The size is based on number of font characters.

If width is set to 10ch the element will have width of 10 characters. So the exact width will depend on given font so ti can not be expressed exactly in pixels. It will differ with different font.

See [[Episode 4 - Typography]] we can limit width size of all paragraphs.