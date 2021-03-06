# Components

A _component_ can be any combination of elements that are styled together to
create a larger component.

## Examples

- [A Simple Card](https://janegca.github.io/examples/web-components/simple-card/simple-card.html)
  A simply styled card from a [freeCodeCamp](https://freecodecamp.org) "Applied
  Visual Design" example

## Web Components

True _Web components_ are custom HTML elements with their own JS API that
encapsulates their functionality, style and markup using a _Shadow DOM_ and
_HTML Template_, allowing for their re-use without fear of colliding with other
code.

There are four lifecycle methods associated with them:

- `constructor()` creates the element
- `connectedCallback()` called when the element is added to the DOM
- `disconnectedCallback()` called when the element is removed from the DOM
- `attributeChangedCallback()` called whenever the value of a component's
  attribute changes

## Examples

- [User Card](https://janegca.github.io/examples/web-components/user-card/user-card.html)
  A custom user card with photo, text, and a hide/show info button and some
  styling.

References:

- [MDN Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components)
