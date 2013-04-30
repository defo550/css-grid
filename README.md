# CSS Grid

A simple grid that I have used across multiple projects for the last year or so.  It is built using [SASS](http://sass-lang.com/) and uses fractional ( or percentage ) widths.


## Class Syntax

### Row

  A `row` groups the columns (i.e. `span-` classes) together in a horizontal row, similar to how a table row works in tables.

  ```html

  <div class="row"></div>
  ```

### Row Modfifiers

  - `row--spacing` will add top and bottom margin to your row.
  - `row--padding` will add padding to the entire row.

    ```html

    <div class="row--spacing"></div>

    <div class="row--padding"></div>
    ```

### Span's

  The `span-` is the base class and is resposible for splitting a `row` into sections.

  ```css

  [span*="span-"] {
    float: left;
  }
  ```

### Span Dimensions

  The span dimension represents the fractional width for the `span-` base class by providing a width rule.  Making it work similar to a table-cell.

  ```css

  .span-1-2 {
    width: 50%;
  }

  .span-1-4 {
    width: 25%;
  }
  ```
