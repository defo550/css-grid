# CSS Grid


CSS Grid is a lightweight grid framework that is non-float based.  Utilizes [SASS](http://sass-lang.com/)'s [placeholder]([http://sass-lang.com/documentation/file.SASS_REFERENCE.html#placeholder_selectors_) functionality to easiy extend and create your own selectors, modifiers, and sub-modules for your project needs.  CSS grid leverages the `inline-block` value for the `display` property.

I like this approach for a couple of reasons:
 1. No clearfix required.
 2. Some control over vertical alignment.
 3. Does not require that I wrap every row of cells in a grid container.

## Class Syntax

There are two main placeholders: `%grid` and `%cell`.  Extend them like so:

  ```css
    .main {
      @extend %grid;
    }

    .sidebar {
      @extend %cell;

      width: 25%;
    }

    .content {
      @extend %cell;

      width: 75%;
    }
  ```

See [_grid.scss](https://github.com/defo550/css-grid/blob/master/css/libs/_grid.scss) for examples creating your standard grid and cell modules.

### Cell Dimensions

To break a grid up into sections, just run the `build-grid()` mixin.  This mixin will generate percentage based objects.

`build-grid()` takes 3 arguments:
  1. A required `$prefix` to name your cell modules.
  2. A space separated list of numbers to create your cell dimesnions (in percentages).
  3. An optional `$suffix`, for creating modifiers, etc.

Example:

  ```css
    $prefix : 'cell-';

    [class*="#{cell-}"] {
      @extend %cell;
    }

    @include build-grid( $prefix, 2 4, '--tablet' );
    @include build-grid( $prefix, 2 4, '--desktop' );

    // Will output
    [class*="cell-"] {
      display: inline-block;
      width: 100%;
      margin: 0;
      padding: 0 0 0 24px;
      letter-spacing: normal;
      vertical-align: top;
     }

    .cell-1-2--tablet,
    .cell-2-4--tablet {
      width: 50%;
    }

    .cell-1-4--tablet {
      width: 25%;
    }

    .cell-3-4--tablet {
      width: 75%;
    }

    .cell-1-2--desktop,
    .cell-2-4--desktop {
      width: 50%;
    }

    .cell-1-4--desktop {
      width: 25%;
    }

    .cell-3-4--desktop {
      width: 75%;
    }
  ```

## Installation

1. [Install SASS](http://sass-lang.com/install) v3.2.0 or greater.
  - **Note**: SASS has a Ruby dependency.
2. clone repo: `git clone https://github.com/defo550/css-grid.git`


## Browser Support
 1. Chrome
 2. Firefox
 3. Opera
 4. Safari
 5. IE 8+
  - **Note**: Should work in IE8, but I did no testinig in any version of IE.

## License

MIT license
