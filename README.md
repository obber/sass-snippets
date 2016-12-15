# SASS/SCSS Snippets

## A collection of useful sass modules to be used in various projects

# How to use:

Copy-paste the desired sass partial into your project.

To grab all of them, clone down this repository into your sass project folder, then include the _all.scss partial.

# Usage:

## _all.scss

`@import` this file if you want all of the sass partials in this repository.

## _colors.scss

Exposes the `palette` function (shorthand: `pal`), which returns a hexidecimal color code.

**Usage:**

```scss
@import '/path/to/colors';

.container {
  color: palette("gray");
  border: 1px solid palette("gray", -20);
}

h1 {
  color: palette("accent-pink");
  text-shadow: 0 1px 1px palette("accent-pink", -10);
}
```

## _mediaQueries.scss

Exposes the `breakpoints` mixin, which accepts a content block and wraps it inside the media query.

The media queries are intended to be used in a mobile-first fashion.

**Usage:**

```
.container {
  display: block;

  @include breakpoint(small) {
    display: inline-block;
  }
}
```