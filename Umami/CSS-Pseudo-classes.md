uplinks:: [[Frontend MOC]]
tags:: #type/thing❖ #status/grown🌳  #on/css

# CSS-Pseudo-classes
---
## Jot down...

A symbole of Pseudo-classes = :

> [!note]
> **Note:** In contrast to pseudo-classes, [[CSS-Pseudo-elements]] can be used to style a _specific part_ of an element.
> 

A [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) **_pseudo-class_** is a keyword added to a selector that *specifies a special state* of the selected element(s).

For example, [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) can be used to change a button's color when the user's pointer hovers over it.

```
/* Any button over which the user's pointer is hovering */

button:hover {
  color: blue;
}
```

Not only in relation to the content of the document tree, but also allow to apply an element to the external factors like the history of navigation (` :visited` ) or the position of the mouse (like [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover), which lets you know if the mouse is over an element or not).

---
## References
- https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes
- xExtracted from: [[2022-06-05-Sun]]