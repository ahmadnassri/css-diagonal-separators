# Gradient Background Image

## ✔ Simple CSS

```css
:root {
  --width: 100%;
  --height: 100px;
  --top-color: #f44336;
  --bottom-color: #2196F3;
}

.separator {
  width: var(--width);
  height: var(--height);
  background-image: linear-gradient(to bottom right, var(--top-color), var(--top-color) 50%, var(--bottom-color) 50%, var(--bottom-color));
}
```

###### Reversed

```css
.separator.reverse {
  background-image: linear-gradient(to bottom left, var(--top-color), var(--top-color) 50%, var(--bottom-color) 50%, var(--bottom-color));
}
```

###### Reversed Vertical

```css
.separator.vertical.reverse {
  background-image: linear-gradient(to top right, var(--top-color), var(--top-color) 50%, var(--bottom-color) 50%, var(--bottom-color));
}
```

- 👎 Jagged / blurry edges on some rendering engines
  - tweak the percentage a little to get a better rounding algorithm.
- 👎 Further control is limited
  - example: creating a shadow effect using `box-shadow`
- 👍 The angle is controlled by the element height value
- 👋 The example above uses [CSS Variables][css-vars] for demonstration purposes, adjust for your own use
  - _css variables are [not fully supported yet][css-vars-compat]._
- 👋 `reversed` & `vertical` variants listed above are verbose for demonstration purposes
  - for simple multi directional classes, use the [`rotate()`][css-transform-rotate] function as needed
  - _see [`style.css`](style.css) for an example_
- 👌 Use with `transparent` colors _(e.g. to overlay an image, or content)_ will require `absolute` or manual positioning:
  - _see [`layout.css`](../layout.css) for an example_

## ✔ Generated Content

Can be used with the `::before` and `::after` pseudo-elements to generate HTML content for the separator without directly modifying your DOM.

###### Example

```css
section {
  ...
}

section::after {
  width: 100%;
  height: 50px;
  background-image: linear-gradient(to bottom right, yellow, yellow 50%, black 50%, black);
}
```

## ✖ Cross Browser Support

[Partial support](http://caniuse.com/#feat=css-gradients)

> Supported in all major browsers, with the exception of `Opera Mini`.

## ✔ Performance

![](performance.png)

## Demo

View [Demo][demo], Play on [CodePen][pen], or inspect the [source files](index.html).

[demo]: https://raw.githack.com/ahmadnassri/css-diagonal-separators/master/gradients/index.html
[css-vars]: https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables
[css-vars-compat]: http://caniuse.com/#search=variables
[css-transform-rotate]: https://www.w3.org/TR/css-transforms-1/#funcdef-rotate
[pen]: http://codepen.io/ahmadnassri/pen/aBrPKb
