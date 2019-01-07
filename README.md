# Spaceman Docs
v0.0.1

* [Getting Started](#getting-started)
  * [About Spaceman](#about-spaceman)
  * [Browser Support](#browser-support)
  * [Installation](#installation)
  * [Build Process](#build-process)
* [Guidelines](#guidelines)
  * [Language](#language)
  * [Naming Pattern](#naming-pattern)
  * [Folder Structure](#folder-structure)
* [Layout](#layout)
  * [Breakpoints](#breakpoints)
  * [Colors](#colors)
  * [Grid](#grid)
  * [Spacing](#spacing)
  * [Typography](#typography)
* [Components](#components)
  * [Buttons](#buttons)
  * [Form Elements](#form-elements)
  * [Hero Image](#hero-image)
* [Utilities](#utilities)
  * [Display](#display)
  * [Floating](#floating)
  * [Position](#position)
  * [Z-index](#z-index)
  * [Sizing](#sizing)
  * [Responsive Visibility](#responsive-visibility)
  * [Miscelaneos](#Miscelaneos)

## Getting Started

### About Spaceman

Spaceman is a simple and easily customizable HTML/CSS boilerplate to build websites and apps. It provides a flexbox based responsive layout system, pre-set styles for basic UI elements and a few CSS utilities and components.

It was designed and built not to be used as a component or a framework, but as a solid and stable base for you to costumize and build your projects upon.

### Browser Support

Spaceman was built using modern CSS and JS features, thus being compatible with the latest releases of all major browsers and platforms. It provides some backwards compatibility but it is limited depending on your needs:

Browser | Version
--- | ---
Chrome | 29+
Microsoft Edge | 12+
Internet Explorer | 10+
Firefox | 22+
Safari | 6.1+
Opera | 12+

### Installation

Spaceman uses [Gulp](http://gulpjs.com/) and [Browsersync](https://www.browsersync.io/), so you'll need [Node.JS](https://nodejs.org/en/). Once you have set it up, [download Spaceman](https://github.com/victordieggo/spaceman/releases/latest) to your project directory and access the terminal:

```
# install gulp globally
$ npm install -g gulp

# go to your project directory
$ cd myproject

# install dev dependencies:
$ npm install

# initialize gulp and browsersync:
$ gulp
```

### Build Process
Section content goes here.

## Guidelines

### Language
Section content goes here.

### Naming Pattern
Section content goes here.

### Folder Structure

At first, the folder structure for your project will be exactly like the example below, it is important to keep this same structure so you don't break the Gulp build process:

```
spaceman/
├── assets/
│   ├── dist/
│   │   ├── css/
│   │   │   ├── main.css
│   │   │   └── ...
│   │   ├── img/
│   │   │   ├── slide.jpg
│   │   │   └── ...
│   │   ├── js/
│   │   │   ├── main.js
│   │   │   └── ...
│   │   └── svg/
│   │       ├── icon-arrow-alt.svg
│   │       ├── icon-arrow.svg
│   │       ├── icon-check.svg
│   │       ├── icon-close.svg
│   │       └── icon-menu.svg
│   │       └── ...
|   └── src/
|       ├── css/
│       │   ├── base/
│       │   │   ├── _grid.scss
│       │   │   ├── _module.scss
│       │   │   ├── _reset.scss
│       │   │   ├── _typography.scss
│       │   │   └── ...
│       │   ├── components/
│       │   │   ├── _buttons.scss
│       │   │   ├── _form-elements.scss
│       │   │   ├── _hero-image.scss
│       │   │   ├── _module.scss
│       │   │   └── ...
│       │   ├── config/
│       │   │   ├── _config.scss
│       │   │   ├── _module.scss
│       │   │   └── ...
│       │   ├── layout/
│       │   │   ├── _footer.scss
│       │   │   ├── _header.scss
│       │   │   ├── _module.scss
│       │   │   ├── _navigation.scss
│       │   │   └── ...
│       │   ├── utils/
│       │   │   ├── _functions.scss
│       │   │   ├── _helpers.scss
│       │   │   ├── _mixins.scss
│       │   │   ├── _module.scss
│       │   │   └── ...
│       │   └── vendor/
│       │       ├── _module.scss
│       │       └── ...
│       ├── img/
│       │   ├── slide.jpg
│       │   └── ...
│       ├── js/
│       │   ├── vendor/
│       │   │   ├── vendor.js
│       │   │   └── ...
│       │   ├── navigation.js
│       │   └── ...
│       └── svg/
│           ├── icon-arrow-alt.svg
│           ├── icon-arrow.svg
│           ├── icon-check.svg
│           ├── icon-close.svg
│           └── icon-menu.svg
│           └── ...
├── .eslintignore
├── .eslintrc
├── .gitignore
├── .stylelintrc
├── gulpfile.js
├── index.html
├── package.json
├── package-lock.json
├── README.md
└── ...
```
#### Styles

Spaceman uses Sass and the SCSS syntax. Each subdirectory in the `assets/src/css` path has a `_module.scss` partial, which references all the styles in that same subdirectory. All the module partials are then referenced `main.scss` file in the root directory.

Out of the box, you will see the following structure:

* `base/` - contains global styles, such as resets, typography and grid
* `components/` - contains each self-contained component in its own `.scss` partial
* `config/` - contains all the global variables, such as colors, breakpoints and etc.
* `layout/` - contains styling for larger layout components such as nav, header, footer, etc.
* `utils/` - contains global mixins, functions and helper selectors
* `vendor/` - contains any 3rd-party styles used in the project
* `main.scss` - output file that brings together all styles

In your projects, you can create any subdirectory (e.g. `pages/` or `themes/`) to organize your styles as long as you follow this same logic, otherwise your styles will not be included in the build process or it will break.

#### Javascript
Section content goes here.

## Layout

### Breakpoints

Spaceman uses the following predefined breakpoints for layout, grid system, and components:

Breakpoint | Syntax | Size
--- | --- | ---
Extra Small | xs | 480px
Small | sm | 600px
Medium | md | 840px
Large | lg | 960px
Extra Large | xl | 1280px

#### Breakpoint Variables

The predefined breakpoints can be overridden in the `_config.scss` partial, using the `$breakpoints` variable. For each breakpoint, a key and a value must be set:

```css
$breakpoints: (
  xs: 480px,
  sm: 600px,
  md: 840px,
  lg: 960px,
  xl: 1280px
);
```
#### Media Query Mixins

All the media queries are available via the mixin `media-breakpoint()`, which uses as parameters the key defined in the `$breakpoints` variable (or a custom value) and the `min` or `max` keyword. Since Spaceman was built using a mobile first approach, the default value for the second parameter is `min`.

#### Examples

**1)** Using the `media-breakpoint()` mixin with default values:

Source Code:
```css
@include media-breakpoint(md) {
  .element {
    display: block;
  }
}
```

CSS:
```css
@media (min-width: 840px) {
  .element {
    display: block;
  }
}
```

**2)** Using the `media-breakpoint()` mixin with custom values:

Source Code:
```css
@include media-breakpoint(980px, max) {
  .element {
    display: block;
  }
}
```

CSS:
```css
@media (max-width: 980px) {
  .element {
    display: block;
  }
}
```

### Colors
Section content goes here.

### Grid
Section content goes here.

### Spacing
Section content goes here.

### Typography
Section content goes here.

## Components

### Buttons
Section content goes here.

### Form Elements
Section content goes here.

### Hero Image
Section content goes here.

## Utilities

### Display
Section content goes here.

### Floating
Section content goes here.

### Position
Section content goes here.

### Z-index
Section content goes here.

### Sizing
Section content goes here.

### Responsive Visibility

The responsive visibility utilities allows you to hide and show elements on a specific [breakpoint](#breakpoints).

#### Hiding elements

To hide an element on a specific breakpoint, you can use the classes  `hide-xs`, `hide-sm`, `hide-md`, `hide-lg` and `hide-xl`.

| | 480px | 600px | 840px | 960px | 1280px
--- | --- | --- | --- | --- | ---
hide-xs | | visible | visible | visible | visible
hide-sm | | | visible | visible | visible
hide-md | | | | visible | visible
hide-lg | | | | | visible
hide-xl | | | | |

* `hide-xs` - hides the element when the viewport width is smaller or equal to **480px**
* `hide-sm` - hides the element when the viewport width is smaller or equal to **600px**
* `hide-md` - hides the element when the viewport width is smaller or equal to **840px**
* `hide-lg` - hides the element when the viewport width is smaller or equal to **960px**
* `hide-xl` - hides the element when the viewport width is smaller or equal to **1280px**

#### Showing elements

To show an element on a specific breakpoint, you can use the classes  `show-xs`, `show-sm`, `show-md`, `show-lg` and `show-xl`.

| | 480px | 600px | 840px | 960px | 1280px
--- | --- | --- | --- | --- | ---
show-xs | visible | | | |
show-sm | visible | visible | | |
show-md | visible | visible | visible | |
show-lg | visible | visible | visible | visible |
show-xl | visible | visible | visible | visible | visible

* `show-xs` - shows the element when the viewport width is smaller or equal to **480px**
* `show-sm` - shows the element when the viewport width is smaller or equal to **600px**
* `show-md` - shows the element when the viewport width is smaller or equal to **840px**
* `show-lg` - shows the element when the viewport width is smaller or equal to **960px**
* `show-xl` - shows the element when the viewport width is smaller or equal to **1280px**

### Miscelaneos
Section content goes here.
