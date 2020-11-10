# CUBE CSS

Notes and examples related to the _Composition Utility Block Exception (CUBE)
CSS_ methodology for writing CSS articulated by
[Andy Bell](https://piccalil.li/blog/cube-css/). Central to the methodology is
the leveraging of CSS' _cascading_ ability which the methodology utilizes and
extends.

> The core of this methodology is that most of the work is already done for you
> with global and high-level styles. This means that... your typography is
> mostly set, your colours are working great and your elements are working
> harmoniously with each other. We [then] use the rest of the methodology...not
> to style everything, but instead, to provide contextual styles that deviate
> from the common, global system...CUBE CSS in essence, is a progressive
> enhancement approach...

Like CSS itself, this methodology scales well. Main principles are:

- **progressive enhancement** define a minimum, global style supported by old
  browsers and then build on it using more modern capabilities; CSS itself
  ensures these will fail silently in older browsers rather than produce errors
  that will break the site
- **reduced abstraction** only abstract what is necessary
- **tool agnostic** methodology can be applies using CSS, SaSS, Less, PostCSS or
  CSS-in-JS; it is more of a "thinking and organisational methodology than a
  tooling methodology"

CSS itself is an "incredibly complex programming language" because you need to
understand not only the syntax but _how it works_.

## Composition

> The composition layer’s job is to create flexible, component-agnostic layout
> systems that support as many variants of content as possible.

- design on the macro-level with layout rules being _suggested_ rather than
  strict, allowing the browser be the final arbiter
- "think of the composition as a skelton"
- regardless of how many micro-levels you break your design into they will
  _always_ be shown in a larger context
- also applies at the micro-level where components are _composed_
- the composition layer should:
  - provide high-level, flexible layouts
  - determine how element interact with each other
  - create consistent flow and rhythm
- what the composition layer should **not**
  - provide visual treatment such as color or font styles
  - provide decorative styles such as shadows or patterns
  - force a browser to provide a pixel perfect layout instead of a flexible,
    progressive layout

## Utility

- a _utility_ is a "CSS class that does one job and does it well" [like pure
  functions in programming languages?]
- utility classes are used to apply _design tokens_ in the context of our design

### Design Tokens

> Design Tokens are the visual atoms of the design system – specifically, they
> are named entities that store visual design attributes. We use them in place
> of hard–coded values in order to maintain a scalable and consistent visual
> system. **_Jina_**

## Block

- a block a building block or component i.e. a button or card
- blocks or components usually have classnames applied i.e. `.my-block .title`
  or `.my-block h2`

## Exceptions

- small variations to a block identified by their data attributes i.e.
  `data-state="reversed"`

## Grouping

- Bell likes to group classes using `[]`

```html
<article
  class="[ card ] [ section box ] [ bg-base color-primary ]"
  data-state="reversed"
></article>
```

although you can also use pipes, if you prefer

```html
<article
  class="card | section box | bg-base color-primary"
  data-state="reversed"
></article>
```

- regardless, uses the same order
  1. the main block class
  1. any subsequent block class
  1. utility classes
