# P12–P13 — CSS Grid and Flexbox

## P12 — Build a responsive projects grid

The portfolio uses CSS Grid to arrange project cards in two equal columns on larger screens and one column on smaller screens.

\`\`\`css
.projects-grid {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 42px 24px;
}

@media (max-width: 680px) {
  .projects-grid {
    grid-template-columns: 1fr;
  }
}
\`\`\`

### Why Grid?

The project cards form a collection with rows and columns. Grid makes both dimensions explicit and keeps the columns aligned. The \`minmax(0, 1fr)\` pattern allows tracks to shrink without overflowing because of long content.

Try changing the desktop declaration to:

\`\`\`css
grid-template-columns: repeat(3, minmax(0, 1fr));
\`\`\`

Then resize the browser and observe how the media query restores a single column on a narrow screen.

## P13 — When should you use Flexbox or Grid?

| Layout need | Flexbox | CSS Grid |
| --- | --- | --- |
| Navigation in one row | Excellent | Possible |
| Aligning a button and text | Excellent | Usually unnecessary |
| Equal card columns and rows | Possible, less direct | Excellent |
| A page with main content and sidebar | Possible | Excellent |
| Centering items along one axis | Excellent | Possible |
| Two-dimensional placement | Not its main purpose | Excellent |

### Examples from this project

**Flexbox is used for:**
- Header: brand on the left, navigation on the right.
- Hero: introduction next to a learning panel.
- Contact section: text and call-to-action side by side.
- Footer: logo, description, and back-to-top link.
- Navigation links and small groups of buttons.

**Grid is used for:**
- Skills: a consistent set of skill cards.
- Projects: aligned project columns.
- About section: heading and descriptive text columns.
- Newspaper: main story and sidebar columns.
- Newspaper feature articles: two-column editorial section.

### A practical decision rule

Choose Flexbox when you are arranging items along one main axis (a row or a column) and the content should influence how much space each item takes.

Choose Grid when you need control over rows and columns together, consistent tracks, or a larger page-level layout.

They are not competitors. A common pattern is to use Grid for the page structure and Flexbox inside each component.

### Experiment

1. Inspect the navigation in \`css/styles.css\`. It uses Flexbox.
2. Inspect \`.projects-grid\`. It uses Grid.
3. Temporarily change the project grid to one column.
4. Resize your browser to mobile width.
5. Restore the original CSS and explain why Grid is a natural choice for the cards while Flexbox is a natural choice for the navigation.
