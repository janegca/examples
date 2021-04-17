# Understanding `z-index` and Stacking Contexts

Stacking contexts and the `z-index` property are closely connected and can be
influenced by any number of properties from `position` to `isolation` as
summarized in the blog post
[Putting Things on Top of Other Things](https://tellthemachines.com/stacking-contexts/):

```javascript
z - index !== "auto" &&
  (position !== "static" || parentElement.style.display === ("flex" || "grid"));

opacity !== 1;
transform !== "none";
mix - blend - mode !== "normal";
filter !== "none";
perspective !== "none";
isolation === "isolate";
position === "fixed";
```

The post was written in 2018, today we can also include the `will-change`
property and some values of the `clip-path` property. There may be more (haven't
been able to find a complete list within the standard pages themselves).

- [Normal Order](https://janegca.github.io/examples/css/z-index/01-normal-order.html)
- [Normal Order and Position](https://janegca.github.io/examples/css/z-index/02-normal-with-positioning.html)
- [Position and z-index](https://janegca.github.io/examples/css/z-index/03-norm-pos-z-index.html)
- [Position and z-index again](https://janegca.github.io/examples/css/z-index/04-norm-pos-z-index-2.html)
- [Creating A New Stacking Context](https://janegca.github.io/examples/css/z-index/05-new-stacking-context.html)
- [Opacity, Transform and Filter](https://janegca.github.io/examples/css/z-index/06-opacity.html)
- [Opacity, Transform and Filter without Position Being Set](https://janegca.github.io/examples/css/z-index/06a-opacity-no-pos.html)
- [Negative z-index Values](https://janegca.github.io/examples/css/z-index/07-neg-z-index.html)
- [Effect of `overflow: hidden`](https://janegca.github.io/examples/css/z-index/08-overflow.html)
- [z-index in Flex or Grid Layouts](https://janegca.github.io/examples/css/z-index/09-flex-grid.html)
- [z-index and isolation and mix-blend-mode](https://janegca.github.io/examples/css/z-index/10-isolate-mix-blend.html)

# Source Code for examples

- [Github](https://github.com/janegca/examples/tree/main/css/z-index)
- [Codepen](https://codepen.io/collection/yrBaLB)

# References:

## Standards and MDN

- [`z-index` (CSSWG)](https://drafts.csswg.org/css2/#propdef-z-index)
- [Understanding CSS `z-index` (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index)

- [An Elaborate Description of Stacking Contexts (W3C)](https://www.w3.org/TR/CSS22/zindex.html)

- [The Stacking Context (MDN)](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Positioning/Understanding_z_index/The_stacking_context)

## Articles

- [`z-index` (Codrops)](https://tympanus.net/codrops/css_reference/z-index/)
- [Understanding `z-index` in CSS (Shaheed Ahmad)](https://www.ishadeed.com/article/understanding-z-index/)
- [Solve your z-index issues | z-index and stacking context explained (Kevin Powell)](https://www.youtube.com/watch?v=uS8l4YRXbaw)
- [What No One Told You About Z-Index (Walton)](https://philipwalton.com/articles/what-no-one-told-you-about-z-index/)
- [Putting Things on Top of Other Things](https://tellthemachines.com/stacking-contexts/)
