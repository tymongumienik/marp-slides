# Agent Notes

## HTML `<div>` rendering in Marp

**Always remove blank lines between sibling `<div>` elements.** In Marp (CommonMark), blank lines terminate raw HTML blocks. A blank line between two sibling `<div>` elements causes Marp to treat them as separate HTML blocks, which can insert unwanted `<p>` tags or break flex/grid layouts.

### Correct:
```html
<div class="card">Card 1</div>
<div class="card">Card 2</div>
<div class="card">Card 3</div>
```

### Wrong (causes rendering issues):
```html
<div class="card">Card 1</div>

<div class="card">Card 2</div>

<div class="card">Card 3</div>
```

This applies to all sibling HTML elements (`<div>`, `<span>`, `<details>`, etc.) at the same nesting level. Nested children inside a parent wrapper are fine.
