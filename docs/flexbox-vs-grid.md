# P12–P13 — Portfolio Grid & Choosing a Layout System

## P12 — Portfolio projects grid

The portfolio's project cards use CSS Grid:

```css
.project-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 1.4rem;
}
@media (max-width: 760px) {
  .project-grid { grid-template-columns: 1fr; }
}
```

Grid is a good fit because the cards form a two-dimensional collection: rows and columns are both important. The `minmax(0, 1fr)` tracks prevent long content from forcing a column wider than its container.

## P13 — Choosing between Flexbox and Grid

| Requirement | Flexbox | CSS Grid |
| --- | --- | --- |
| One row or one column | Best fit | Possible, but often unnecessary |
| Rows and columns together | Can wrap, but tracks are independent | Best fit |
| Navigation items in a row | Best fit | Possible |
| Consistent card columns | Less direct | Best fit |
| Aligning items along one axis | Best fit | Possible |
| Page-level editorial layout | Possible, but awkward | Best fit |

### Examples in this repository

- **Flexbox:** header navigation, hero content, about section, contact section, footer, and skill-card internals.
- **Grid:** portfolio project cards, skill tiles, newspaper content/sidebar, and newspaper article columns.

### Decision rule

Start with Flexbox when arranging items along one primary axis and their natural sizes should influence the layout. Start with Grid when you need explicit rows and columns or consistent two-dimensional alignment. They are complementary; a real page commonly uses both.

### Practical test

Resize the browser from desktop to mobile. The project cards change from two columns to one, while the navigation and footer rearrange with Flexbox. The newspaper layout moves its sidebar below the main story at the tablet breakpoint.
