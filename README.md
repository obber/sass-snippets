# SASS/SCSS Snippets

## A collection of useful sass modules to be used in various projects

# How to use:

Copy-paste the desired sass partial into your project.

To grab all of them, clone down this repository into your sass project folder, then include the _all.scss partial.

# Usage

## _all.scss

`@import` this file if you want all of the sass modules & classes in this repository.

# Modules

Modules are sass partials that provide re-usable encapsulations of configurations and/or logic that **does not** actually output any scss. They are primarily useful in your own scss rules, mixins, modules, etc.

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

```scss
.container {
  display: block;

  @include breakpoint(small) {
    display: inline-block;
  }
}
```

# Classes

Class sass partials **will** output scss if imported. They are helper classes to implement common effects in scss. e.g. color name classes for buttons which provide standard `:hover` & `:active` selection rules.

## _colorHovers.scss

**Dependencies:** `modules/_colors.scss` (or define your own `$colors` scss map)

Maps every color name in the `$colors` map of `modules/_colors.scss` so that each color is output as a class rule. It comes with `:hover` & `:active` selector rules which alters the `background-color` of the element by 10% lighter (hover) and -10% darker (active).

**Usage:**

HTML:   
```html
<button class="blue">
  Hello World
</button>
```

SCSS:   
```scss
// import the colors module dependency
@import './modules/colors';

/*
or define your own color map:
$colors: (
  "blue": #398ac7,
);
*/

@import './classes/colorHovers';
```
