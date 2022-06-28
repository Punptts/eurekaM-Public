uplinks:: [[Frontend MOC]]
tags:: #type/thing❖ #status/develop🔧 #on/css 

# CSS-Display grid
---
## Jot down...
Grid is a grid based 2D layout system, **made up of rows and columns**. This help in solving problem of creating advanced global and miccro layout.

For example, in the context of DashboardJoe, we have got row and column and that is why we use grid system to manage the site layout.

Syntax
- grid: start
- grid: center
- grid: justify-item
- grid: place-content

First property to use when using grid, 

```
.example {
	display: grid;
	grid-template-columns: repeat (3, 3rem);
	grid-template-rows: 4rem 2rem;
}

.card {
	display: grid;
	grid-template-columns: auto 4rem;
	grid-template-rows: 4rem 2 rem;
}

.card {
	display: grid;
	grid-template-columns: 3rem repear (7, 1fr);
}

```

- grid-template-areas
- then set grid area (use for Menu item)

auto = all the rest

---

Contrast of grid **Flex box**
Flex = 1 row or 1 column / vertical or horizontal
Flex-wrap = makes 1d into 2d system of flex (similar to grid)

- Flex: flex-start
- Flex: flex-center
- Flex: justify-content
- Flex: place-item

We can summarized as "grid is for layout and flex box is for alignment"

---
## References
- DashboardJoe part 4
- xExtracted from: [[2022-06-05-Sun]]