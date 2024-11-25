# CSS_GRID
ACT 27 CSS GRID

CSS Grid
CSS Grid is a two-dimensional layout system that enables web developers to create complex,
responsive grid-based layouts with ease. Unlike Flexbox, which is primarily one-dimensional (either row or column), 
CSS Grid allows you to control both rows and columns at the same time, giving you greater control over complex layouts.

CSS Grid is highly useful when you want to create layouts with multiple rows and columns, as it simplifies positioning 
and responsiveness, without needing to rely on floats or positioning.

Key Concepts of CSS Grid:
Grid Container: The parent element that uses the grid layout. You define a grid container by setting the display property to grid or inline-grid.

.container {
  display: grid;
}

Grid Items: The child elements inside the grid container. These are automatically placed into the grid layout by CSS.

Grid Lines: The lines that form the boundaries of rows and columns. Grid lines can be referenced by their number (e.g., 1, 2, 3, etc.) or by their name if a named grid line is defined.

Grid Tracks: The space between two adjacent grid lines. A grid track is either a row track (between horizontal lines) or a column track (between vertical lines).

Grid Cells: The intersection of a grid row and a grid column. Each grid item is placed inside one or more grid cells.

Grid Areas: A grid area is a rectangular space formed by the intersection of grid lines. You can assign grid items to a specific grid area using the grid-area property.

Key CSS Grid Properties:
1. Properties for the Grid Container
a. display
Defines an element as a grid container.
Values:
grid: Defines a block-level grid container.
inline-grid: Defines an inline-level grid container.

.container {
  display: grid;
}


grid-template-columns
Defines the number of columns and their size.
Values: A space-separated list of lengths, percentages, or fr units (fractional units).
auto: Columns take up space based on their content.
fr: Fractional units that divide the container's space.

.container {
  grid-template-columns: 1fr 1fr 1fr;  /* Creates 3 equal-width columns */
}

 grid-template-rows
Defines the number of rows and their size.
Values: Similar to grid-template-columns, can use length units, percentages, or fr.
css
Copy code
.container {
  grid-template-rows: 100px auto 200px;  /* 3 rows with different heights */
}
d. grid-template-areas
Allows you to define named grid areas, providing a way to visually lay out the grid. This helps in positioning items.
Values: A space-separated list of strings, each representing a row of grid areas.
css
Copy code
.container {
  grid-template-areas: 
    "header header header"
    "sidebar main main"
    "footer footer footer";
}
e. gap (formerly grid-gap)
Defines the space between grid items, both between rows and columns.
Values: Length values (e.g., 10px).
css
Copy code
.container {
  gap: 20px;  /* Adds 20px gap between rows and columns */
}
f. grid-auto-columns and grid-auto-rows
Defines the size of implicitly created grid columns and rows when items overflow or are added beyond the explicitly defined grid.
css
Copy code
.container {
  grid-auto-columns: 200px;  /* Implicit columns will have a width of 200px */
  grid-auto-rows: 100px;     /* Implicit rows will have a height of 100px */
}
2. Properties for the Grid Items
a. grid-column
Specifies where a grid item should be placed along the columns.
Values: A span or a start and end position, e.g., grid-column: 1 / 3; (item spans from column line 1 to column line 3).
css
Copy code
.item {
  grid-column: 1 / 3;  /* This item will span across the first two columns */
}
b. grid-row
Specifies where a grid item should be placed along the rows.
Values: Similar to grid-column, you can define a span or a start and end position.
css
Copy code
.item {
  grid-row: 2 / 4;  /* This item will span from row line 2 to row line 4 */
}
c. grid-area
A shorthand property for defining both grid-row and grid-column values at once, or for assigning items to named grid areas.
Values: grid-area: row-start / column-start / row-end / column-end;
css
Copy code
.item {
  grid-area: 1 / 1 / 3 / 3;  /* Starts from row 1, column 1, spans to row 3, column 3 */
}
Alternatively, if you used grid-template-areas in the container, you can reference the name of the area:

css
Copy code
.item {
  grid-area: header;  /* Item is placed in the 'header' area */
}
d. justify-self
Aligns an individual grid item along the row axis (horizontal axis).
Values:
start: Align to the start of the grid.
end: Align to the end of the grid.
center: Align to the center.
stretch: Stretch to fill the available space (default).
css
Copy code
.item {
  justify-self: center;  /* Centers the item horizontally */
}
e. align-self
Aligns an individual grid item along the column axis (vertical axis).
Values: Same as justify-self (start, end, center, stretch).
css
Copy code
.item {
  align-self: end;  /* Aligns the item at the bottom of the grid */
}
f. place-self
A shorthand for align-self and justify-self.
css
Copy code
.item {
  place-self: center;  /* Centers the item both horizontally and vertically */
}
Example of a Simple Grid Layout:
css
Copy code
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;  /* 3 columns, with the middle one being twice as wide */
  grid-template-rows: auto 100px;      /* 2 rows, with the second row fixed at 100px */
  gap: 10px;
}

.header {
  grid-column: 1 / 4;  /* Span across all columns */
}

.sidebar {
  grid-row: 2 / 3;  /* Place in the second row */
}

.main {
  grid-column: 2 / 3;  /* Place in the middle column */
}

.footer {
  grid-column: 1 / 4;  /* Span across all columns */
}


<div class="container">
  <div class="header">Header</div>
  <div class="sidebar">Sidebar</div>
  <div class="main">Main content</div>
  <div class="footer">Footer</div>
</div>

Summary of CSS Grid Properties:

Property	Description

display	Defines an element as a grid container (grid or inline-grid).
grid-template-columns	Defines the number and size of columns.
grid-template-rows	Defines the number and size of rows.
grid-template-areas	Defines named grid areas for easy placement of grid items.
gap	Sets the gap (spacing) between grid rows and columns.
grid-auto-columns	Defines the size of implicitly created grid columns.
grid-auto-rows	Defines the size of implicitly created grid rows.
grid-column	Specifies the start and end positions of a grid item along columns.
grid-row	Specifies the start and end positions of a grid item along rows.
grid-area	Shorthand for both grid-row and grid-column or referencing grid areas.
justify-self	Aligns an individual grid item along the row axis (horizontal).
align-self	Aligns an individual grid item along the column axis (vertical).
place-self	Shorthand for both justify-self and align-self.

CSS Grid is an incredibly powerful tool for creating complex layouts with minimal effort. 
It simplifies tasks that used to require many hacks or tricks, like complex multi-column layouts, 
and it integrates perfectly with other layout models such as Flexbox for added flexibility.
