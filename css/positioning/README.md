# Position and Transform

## Positioning Context

- a _positioned element_ is one whose `position` has been changed from the
  default `static` to one of: `absolute`,`fixed`, `relative`, or `sticky`
- a positioned element can be moved about on the page using the _offset
  properties_ `top right bottom left` (these properties have no effect on
  elements with `static` positions)
- the offsets are relative to the elements _positioning context_

### `position: static`

- the default position value, the element maintains its position in the normal
  HTML document flow
- the offset properties (`top left bottom right`) and the `z-index` properties
  have **no effect** on statically positioned elements

Example:
[Position Static](https://janegca.github.io/examples/css/positioning/pos-static.html)

### `position: relative`

- creates a context for itself and its `position: absolute` descendants
- the element's original position is the one it holds in the normal flow
- the element's offset properties are relative to the elements own coordinate
  origin, by default, the elements own _top, left_ corner
- moving the element to a new position does _not_ effect the page flow, the
  space the element took up originally is maintained on the page, the
  re-positioned element will overlap anything found in its new position
- if the element's `z-index` is changed from the default `auto` a new _stacking
  context_ is created

### `position: absolute`

- creates a positioning context relative to another element on the page i.e. a
  positioned ancestor or, if it has no positioned ancestors, the viewport itself
- the elements offset properties will be relative to the coordinate origin of
  the other element i.e. to the top,left of the enclosing parent or the viewport
- when an absolutely positioned element is moved it is _taken out of the normal
  flow_, its original space is _not_ maintained, and it will overlap any element
  found in its new position
- the margins of absolutely positioned elements _do not_ collapse
- an absolutely positioned element is the size of its content, to stretch it to
  fill its parent, set all four offset properties (`top right bottom left`) to
  zero

### `position: fixed`

- creates a positioning context relative to the viewport (unless an ancestor has
  its `transform`, `filter`, or `perspective` property set to other than the
  default `none`)
- the element is taken out of the normal flow (its original space is not
  preserved) and it will overlap any elements found in its new position
- a _fixed_ element is _not_ effected by scrolling; it stays exactly where it is
  'fixed' in the viewport regardless of how the page is moved
- a new stacking context is always created

### `position: sticky`

- creates a positioning context relative to the nearest ancestor's scroll port
- it behaves like a relatively positioned element until a certain point in the
  scroll is reached, at which point it behaves like a `fixed` element
- the _sticking_ point is determined by the offset property values

References:

- [Codrops CSS Reference: position](https://tympanus.net/codrops/css_reference/position/)
- [MDN: position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [W3C CSS3 Draft: position](https://drafts.csswg.org/css-position-3/#propdef-position)

## Transformations

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

### transform-origin

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

References:

- [Codrops CSS Reference: transform](https://tympanus.net/codrops/css_reference/transform/)
- [W3C CSS Transforms Module - Level 1](https://www.w3.org/TR/css-transforms-1/)
- [W3C CSS Transform Editor's Draft](https://drafts.csswg.org/css-transforms)
- [W3Schools: How to Create Circles](https://www.w3schools.com/howto/howto_css_circles.asp)
- [W3Schools: How to Centre a Button Vertically](https://www.w3schools.com/howto/howto_css_center_button.asp)