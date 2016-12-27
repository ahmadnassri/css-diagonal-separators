# CSS Shapes

## ✖ Simple CSS

```css
:root {
  --width: 100%;
  --height: 100px;
  --top-color: #f44336;
  --bottom-color: #2196F3;
}

.separator {
  position: relative;
  width: var(--width);
  height: var(--height);
}

.separator::before {
  position: absolute;
  content: "";
  width: 100%;
  height: 100%;
  background-color: var(--top-color);
  clip-path: polygon(100% 0, 0 0, 0 100%);
}

.separator::after {
  position: absolute;
  content: "";
  width: 100%;
  height: 100%;
  background-color: var(--bottom-color);
  clip-path: polygon(100% 0, 0 100%, 100% 100%);
}
```

###### Reversed

```css
.separator.reverse::before {
  clip-path: polygon(0 0, 100% 0, 100% 100%);
}

.separator.reverse::after {
  clip-path: polygon(0 0, 0% 100%, 100% 100%);
}
```

###### Reversed Vertical

```css
.separator.vertical.reverse::before {
  clip-path: polygon(0 0, 0% 100%, 100% 100%);
}

.separator.vertical.reverse::after {
  clip-path: polygon(0 0, 100% 0, 100% 100%);
}
```

- 👎 Requires the use of generated content
- 👍 The angle is controlled by the element height value
- 👎 Further control is limited
  - example: creating a shadow effect using `box-shadow`
- 👋 The example above uses [CSS Variables][css-vars] for demonstration purposes, adjust for your own use
  - _css variables are [not fully supported yet][css-vars-compat]._
- 👋 `reversed` & `vertical` variants listed above are verbose for demonstration purposes
  - for simple multi directional classes, use the [`rotate()`][css-transform-rotate] function as needed
  - _see [`style.css`](style.css) for an example_
- 👌 Use with `transparent` colors _(e.g. to overlay an image, or content)_ will require `absolute` or manual positioning:
  - _see [`layout.css`](../layout.css) for an example_

## ✖ Generated Content

**Cannot** be used with the `::before` and `::after` pseudo-elements as it relies on them already to generate the HTML content for the separator.

## ✖ Cross Browser Support

[Partial support](http://caniuse.com/#feat=css-clip-path)

## ❓ Performance

> **TODO**

## Demo

View [Demo][demo], Play on [CodePen][pen], or inspect the [source files](index.html).

[demo]: https://raw.githack.com/ahmadnassri/css-diagonal-separators/master/shapes/index.html
[css-vars]: https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables
[css-vars-compat]: http://caniuse.com/#search=variables
[css-transform-rotate]: https://www.w3.org/TR/css-transforms-1/#funcdef-rotate
[pen]: http://codepen.io/ahmadnassri/pen/bByOKv
