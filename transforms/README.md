# CSS3 2D Transforms

## ✖ Simple CSS

```css
:root {
  --width: 300px;
  --height: 100px;
  --top-color: #f44336;
  --bottom-color: #2196F3;
  --vertical-angel: 108.5deg;
  --horizontal-angel: 18.5deg;
}

.separator {
  width: var(--width);
  height: var(--height);
  overflow: hidden;
}

.separator::before {
  display: block;
  content: '';
  width: 100%;
  height: 100%;
  background-color: var(--top-color);
  transform: skewY(calc(-1 * var(--horizontal-angel)));
  transform-origin: bottom left;
}

.separator::after {
  display: block;
  content: '';
  width: 100%;
  height: 100%;
  background-color: var(--bottom-color);
  transform: skewY(calc(-1 * var(--horizontal-angel)));
  transform-origin: bottom left;
}
```

###### Reversed

```css
.separator.reverse::before,
.separator.reverse::after {
  transform: skewY(var(--horizontal-angel));
  transform-origin: bottom right;
}
```

###### Vertical

```css
.separator.vertical::before,
.separator.vertical::after {
  transform: skewY(var(--vertical-angel));
}
```

###### Reversed Vertical

```css
.separator.vertical.reverse {
  position: relative;
}

.separator.vertical.reverse::before {
  position: absolute;
  transform: skewY(calc(-1 * var(--vertical-angel)));
  transform-origin: bottom left;
}

.separator.vertical.reverse::after {
  position: absolute;
  transform: skewY(calc(-1 * var(--vertical-angel)));
  transform-origin: top right;
}
```

**Notes:**

- 👎 Must calculate desired angle manually
- 👎 Must set corrosponding element height value manually
- 👎 Requires the use of generated content
- 👎 Further control is limited
  - _e.g._ creating a shadow effect using `box-shadow`

## ✖ Generated Content

**Cannot** be used with the `::before` and `::after` pseudo-elements as it relies on them already to generate the HTML content for the separator.

## ✖ Cross Browser Support

[Partial support](http://caniuse.com/#feat=transforms2d)

> Supported in all major browsers, with the exception of `Opera Mini`.

## ✖ Performance

![](performance.png)

## Demo

View [Demo][demo], Play on [CodePen][pen], or inspect the [source files](style.css).

[demo]: https://raw.githack.com/ahmadnassri/css-diagonal-separators/master/transforms/index.html
[pen]: http://codepen.io/ahmadnassri/pen/pNmqZQ
