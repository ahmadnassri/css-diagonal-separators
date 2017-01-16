# Pure CSS Diagonal Separators

Read The full [post on Code Pen](https://codepen.io/ahmadnassri/post/non-rectangular-headers-part-1)

> **Notes**:
>
> - [CSS Variables][css-vars] are used for demonstration purposes and future prosperity, they are yet to be [supported][css-vars-compat] across all browsers and rendering engines!
> - The sample code below uses [CSS Variables][css-vars] for demonstration purposes and future prosperity, they are yet to be [supported][css-vars-compat] across all browsers and rendering engines!
> - 👋 `reversed` & `vertical` variants listed below are verbose for demonstration purposes
> - for simple multi directional classes, use the [`rotate()`][css-transform-rotate] function as needed
>   - _see the `style.css` of each method for a detailed example_
> - 👌 Use with `transparent` colors _(e.g. to overlay an image, or content)_ will require `absolute` or manual positioning:
>   - _see the [`layout.css`](assets/layout.css) for a detailed example_

#### Comparision Matrix

Method                                | Simple CSS | Generated Content | Cross Browser Support | Performance
------------------------------------- | ---------- | ----------------- | --------------------- | -----------
[Borders](borders)                    | ✔          | ✔                 | ✔                     | ✖
[CSS Shapes](shapes)                  | ✖          | ✖                 | ✖                     | ✖
[Gradient Background Image](gradient) | ✔          | ✔                 | ✖                     | ✔
[SVG Background Image](svg)           | ❓          | ✔                 | ✔                     | ✔
[SVG Mask](svg-mask)                  | ✖          | ✖                 | ✖                     | ✖
[CSS3 2D Transforms](transforms)      | ✖          | ✖                 | ✖                     | ✖

#### Results

- Simple CSS
  - 🥇 [Borders](borders)
  - 🥈 [Gradient Background Image](gradient)
  - 🥉 [CSS Shapes](shapes)
- Generated Content
  - 🥇 [Borders](borders)
  - 🥈 [Gradient Background Image](gradient)
  - 🥉 [SVG Background Image](svg)
- Cross Browser Support
  - 🥇 [Borders](borders)
  - 🥈 [SVG Background Image](svg)
  - 🥉 [CSS Shapes](shapes)
- Performance
  - 🥇 [Gradient Background Image](gradient)
  - 🥈 [SVG Background Image](svg)
  - 🥉 [Borders](borders)

---

### [Borders](borders)

> ```css
> border-width: ...; border-color: ...;
> ```

- ✔ Simple CSS
- ✔ Generated Content
- ✔ Cross Browser Support
- ✖ Performance

### [CSS Shapes](shapes)

> ```css
> clip-path: polygon(...)
> ```

- ✖ Simple CSS
- ✖ Generated Content
- ✖ Cross Browser Support
- ✖ Performance

### [Gradient Background Image](gradient)

> ```css
> background-image: linear-gradient(...);
> ```

- ✔ Simple CSS
- ✔ Generated Content
- ✖ Cross Browser Support
- ✔ Performance

### [SVG Background Image](svg)

> ```css
> background-image: url(data:image/svg+xml, ...);
> ```

- ❓ Simple CSS
- ✔ Generated Content
- ✔ Cross Browser Support
- ✔ Performance

### [SVG Mask](svg-mask)

> ```css
> mask-image: url(data:image/svg+xml, ...);
> ```

- ✖ Simple CSS
- ✖ Generated Content
- ✖ Cross Browser Support
- ✖ Performance

### [CSS3 2D Transforms](transforms)

> ```css
> transform: skewY(...);
> ```

- ✖ Simple CSS
- ✖ Generated Content
- ✖ Cross Browser Support
- ✖ Performance

[css-vars]: https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_variables

[css-vars-compat]: http://caniuse.com/#search=variables

[css-transform-rotate]: https://www.w3.org/TR/css-transforms-1/#funcdef-rotate
