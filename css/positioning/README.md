# Position Property

## Positioning Context

- a _positioned element_ is one whose `position` has been changed from the
  default `static` to one of: `absolute`,`fixed`, `relative`, or `sticky`
- a positioned element can be moved about on the page using the _offset
  properties_ `top right bottom left` (these properties have no effect on
  elements with `static` positions)
- the offsets are relative to the elements _positioning context_

### [`position: static`](https://janegca.github.io/examples/css/positioning/pos-static.html)

- the default position value, the element maintains its position in the normal
  HTML document flow
- the offset properties (`top left bottom right`) and the `z-index` properties
  have **no effect** on statically positioned elements

### [`position: relative`](https://janegca.github.io/examples/css/positioning/pos-relative.html)

- creates a context for itself and its `position: absolute` descendants
- the element's original position is the one it holds in the normal flow
- the element's offset properties are relative to the elements own coordinate
  origin, by default, the elements own _top, left_ corner
- moving the element to a new position does _not_ effect the page flow, the
  space the element took up originally is maintained on the page, the
  re-positioned element will overlap anything found in its new position
- if the element's `z-index` is changed from the default `auto` a new _stacking
  context_ is created

### [`position: absolute`](https://janegca.github.io/examples/css/positioning/pos-absolute.html)

- creates a positioning context relative to another element on the page i.e. a
  positioned ancestor or, if it has no positioned ancestors, the viewport itself
- the elements offset properties will be relative to the coordinate origin of
  the other element i.e. to the top,left of the enclosing parent or the viewport
- an absolutely positioned element is _taken out of the normal flow_, its
  original space is _not_ maintained, and it will overlap any element found in
  its new position
- the margins of absolutely positioned elements _do not_ collapse
- an absolutely positioned element is the size of its content, to stretch it to
  fill its parent, set all four offset properties (`top right bottom left`) to
  zero
- it always behaves as a block element regardless of its original display type

### [`position: fixed`](https://janegca.github.io/examples/css/positioning/pos-fixed.html)

- creates a positioning context relative to the viewport (unless an ancestor has
  its `transform`, `filter`, or `perspective` property set to other than the
  default `none`)
- the element is taken out of the normal flow (its original space is not
  preserved) and it will overlap any elements found in its new position
- a _fixed_ element is _not_ effected by scrolling; it stays exactly where it is
  'fixed' in the viewport regardless of how the page is moved
- a new stacking context is always created

### [`position: sticky`](https://janegca.github.io/examples/css/positioning/pos-sticky.html)

- creates a positioning context relative to the nearest ancestor's scroll port
- it behaves like a relatively positioned element until a certain point in the
  scroll is reached, at which point it behaves like a `fixed` element
- the _sticking_ point is determined by the offset property values

### [Offset Properties](https://janegca.github.io/examples/css/positioning/pos-offsets.html)

- four offset properties: `top left bottom right`
- have no effect unless the element position has been set to something other
  than the default `static`

### [Stacking Order z-index](https://janegca.github.io/examples/css/positioning/pos-z-index.html)

- z-index establishes an elements stacking order relative to its containing
  block
- any element with a z-index set establishes a stacking context for its
  descendents
- a z-index of `auto` is treated as `z-index: 0`

References:

- [Codrops CSS Reference: position](https://tympanus.net/codrops/css_reference/position/)
- [MDN: position](https://developer.mozilla.org/en-US/docs/Web/CSS/position)
- [W3C CSS3 Draft: position](https://drafts.csswg.org/css-position-3/#propdef-position)
- [Positioning in CSS by Eric A Meyer](https://www.oreilly.com/library/view/positioning-in-css/9781491930366/)
