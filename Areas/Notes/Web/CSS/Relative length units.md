---
up: 
related: 
created: 2024-07-22
tags:
  - css
---

Relative length units are relative to something else. For example:

- `em` and `rem` are relative to the font size of the parent element and the root element, respectively.
- `vh` and `vw` are relative to the viewport's height and width, respectively.

#### ems and rems

**The em unit means "my parent element's font-size"** in the case of typography. The [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements inside the [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) with a `class` of `ems` take their sizing from their parent. So each successive level of nesting gets progressively larger, as each has its font size set to `1.3em` — 1.3 times its parent's font size.

**The rem unit means "The root element's font-size"** (rem stands for "root em"). The [`<li>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/li) elements inside the [`<ul>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) with a `class` of `rems` take their sizing from the root element (`<html>`). This means that each successive level of nesting does not keep getting larger.

However, if you change the `<html>` element's `font-size` in the CSS you will see that everything else changes relative to it — both `rem`- and `em`-sized text.

```css
html {
  font-size: 16px;
}

.ems li {
  font-size: 1.3em;
}

.rems li {
  font-size: 1.3rem;
}
```


```html
<ul class="ems">
  <li>One</li>
  <li>Two</li>
  <li>Three
    <ul>
      <li>Three A</li>
      <li>Three B
        <ul>
          <li>Three B 2</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>

<ul class="rems">
  <li>One</li>
  <li>Two</li>
  <li>Three
    <ul>
      <li>Three A</li>
      <li>Three B
        <ul>
          <li>Three B 2</li>
        </ul>
      </li>
    </ul>
  </li>
</ul>
```
