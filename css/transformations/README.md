# Transformations

- a transform value other than the default `none` creates a new stacking order
  and the element becomes a containing block for children with the property
  `position: fixed` or `position: absolute`
- the `transform` property **transforms** the elements coordinate system,
  leading to the elements "transformation in space" **without** effecting the
  layout (although they can affect overflow)
  - "This means that whatever space the element takes up before you transform
    it, it will still take up after you transform it, and the transformations
    will have no effect on how the elements around the transformed element flow"
    and can trigger scroll bars
- transformations are the result of matrix operations
- transformations can be chained, making the order of transformations important

  - a `rotate` or `skew` effects the entire coordinate system and every
    transformation that comes after

- any applied transforms are relative to the element's `transform-origin`

## [`transform-origin`](https://janegca.github.io/examples/css/transformations/transform-origin.html)

- while any elements default, **initial coordinate system** origin is the top,
  left corner, the default coordinate system for any transform is the center of
  the element: (x,y) = (50%,50%) = (0,0)
  - the %'s are relative to the _rendering box_ (content, border, padding, etc)
    and represent offsets
  - if a `length` (units i.e. px, em, rem, etc.) is used, it represents the
    offset from the top, left corner of the rendering box
  - keywords:
    - x-axis (horizontal): left => 0%, right => 100%
    - y-axis (vertical): top => 0%, bottom => 100%
    - center => (x,y) => 50%, 50%
  - z-value: must always be represented as `length`
- other available transforms:
  - [`transform: translate()`](https://janegca.github.io/examples/css/transformations/transform-translate.html)
  - [`transform: translateX(), translateY()`](https://janegca.github.io/examples/css/transformations/transform-translate-xy.html)
  - [`transform: scale()`](https://janegca.github.io/examples/css/transformations/transform-scale.html)
  - [`transform: rotate(), skewX(), skewY()`](https://janegca.github.io/examples/css/transformations/transform-rotate-skew.html)

References:

- [Codrops CSS Reference: transform](https://tympanus.net/codrops/css_reference/transform/)
- [W3C CSS Transforms Module - Level 1](https://www.w3.org/TR/css-transforms-1/)
- [W3C CSS Transform Editor's Draft](https://drafts.csswg.org/css-transforms)
- [W3Schools: How to Create Circles](https://www.w3schools.com/howto/howto_css_circles.asp)
- [W3Schools: How to Centre a Button Vertically](https://www.w3schools.com/howto/howto_css_center_button.asp)
