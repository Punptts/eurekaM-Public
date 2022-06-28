uplinks:: [[Frontend MOC]]
tags:: #type/thing❖ #status/grown🌳 #on/css

# CSS-Pseudo-elements
---
## Jot down...

A symbole of Pseudo-element = ::

> [!note]
> **Note:** In contrast to pseudo-elements, [[CSS-Pseudo-classes]] can be used to style an element based on its _state_.
> 


A CSS **pseudo-element** is a keyword added to a selector that lets you style a specific part of the selected element(s).

For example, `::first-line` can be use to change the font of the first line of a paragraph.

```

/* The first line of every <p> element. */

p::first-line {
  color: blue;
  text-transform: uppercase;
}
```

Can only use one pseudo-element in a selector. Must appear after the selector element.

```
selector::pseudo-element {
  property: value;
}
```

---
## References
- https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements
- xExtracted from: [[2022-06-05-Sun]]