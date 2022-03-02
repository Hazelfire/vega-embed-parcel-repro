# Parcel build failing on vega-embed

This repository reproduces a problem where parcel build fails on vega-embed,
but for some reason normal parcel dev server does not. I'm thinking this could 
be to do with tree shaking loosing something important.

When I say that it "fails", the build itself succeeds, however opening the build
on a web browser will have an uncaught reference error that looks something like:

```
Uncaught ReferenceError: $02aa360f687032cf$import$5ecbb526cd5c0bbc is not defined
```

vega-embed provides a source map with its build, but the source map points the
error to a nonsense location, so it may be an old one
