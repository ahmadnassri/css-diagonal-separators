# SVG Background Image

## ❓ Simple CSS

> - ✔ Simple = using one variant and external SVG image
> - ✖ Not = embedded SVG as a Data URI requires character escaping and encoding

```css
:root {
  --width: 100%;
  --height: 100px;
}

.separator {
  width: var(--width);
  height: var(--height);
  background-image: url(diagonal.svg);
  background-repeat: no-repeat;
  background-size: 100% 100%;
}
```

###### Reversed

```css
.separator.reverse {
  transform: rotateY(180deg);
}
```

###### Reversed vertical

```css
.separator.vertical.reverse {
  transform: rotateX(180deg);
}
```

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100" preserveAspectRatio="none">
  <polygon fill="#f44336" points="100 0, 0 100, 0 0"/>
  <polygon fill="#2196F3" points="100 0, 0 100, 100 100"/>
</svg>
```

**Notes:**

- 👍 The svg image can either be an external file or embedded as a Data URI for a pure CSS approach
  - _(see [`style.css`](style.css) for an example)_
- 👍 The angle is controlled by the element height value
- 👍 Full control of element & SVG shape
  - _e.g.: creating a shadow effect in SVG_
  - _see [`shadow.svg`](shadow.svg) for an example_
- 👎 Must create an SVG image for every color and directional variant
- 👋 Better suited for use as an embedded SVG with a CSS Preprocessor to easily create variants
  - _see [`style.scss`](style.scss) for an example_

## ✔ Generated Content

Can be used with the `::before` and `::after` pseudo-elements to generate HTML content for the separator without directly modifying your DOM.

###### Example

```css
section {
  ...
}

section::after {
  content: '';
  display: block;
  width: 100%;
  height: 50px;
  background-image: url(diagonal.svg);
  background-repeat: no-repeat;
  background-size: 100% 100%;
}
```

## ✔ Cross Browser Support

[Supported on all browsers](http://caniuse.com/#feat=svg-css)

## ✔ Performance

![](performance.png)

## Demo

View [Demo][demo], Play on [CodePen][pen], or inspect the [source files](style.css).

[demo]: https://raw.githack.com/ahmadnassri/css-diagonal-separators/master/svg/index.html
[pen]: http://codepen.io/ahmadnassri/pen/gLJZoW
