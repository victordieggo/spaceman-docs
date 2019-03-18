# Spaceman Docs

## Summary

* [Getting Started](#getting-started)
  * [About Spaceman](#about-spaceman)
  * [Browser Support](#browser-support)
  * [Installation](#installation)
  * [Contents](#contents)
  * [Starter Template](#starter-template)
  * [Build Tools](#build-tools)
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

It was designed and built not to be used as a component or a framework, but as a solid and stable starting point for you to costumize and build your web projects upon.

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

[Download Spaceman](https://github.com/victordieggo/spaceman/releases/latest) and unzip all files into the root directory of your project. The build system is based on [Gulp](#build-tools), so so you'll need [Node.JS](https://nodejs.org/en/) installed first. Once you have set it up, access the bash/terminal/command line:

```
# install gulp command line utility
$ npm install --global gulp-cli

# go to your project directory
$ cd myproject

# install dev dependencies:
$ npm install

# initialize gulp:
$ gulp
```

### Contents

Once downloaded and unziped, the folder structure you'll see will be exactly like the example below: this is the basic structure for starting your web projects using Spaceman. It provides compiled and minified CSS and JS files, as well as their source code, a [starter template](#starter-template) and all the [build tools](#build-tools) you'll need along the way.

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
│       ├── img/
│       │   ├── slide.jpg
│       │   └── ...
│       ├── js/
│       │   ├── libs/
│       │   │   ├── lib.js
│       │   │   └── ...
│       │   ├── polyfill/
│       │   │   ├── polyfill.js
│       │   │   └── ...
│       │   ├── vendor/
│       │   │   ├── vendor.js
│       │   │   └── ...
│       │   ├── navigation.js
│       │   └── ...
|       ├── sass/
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

### Starter Template
Section content goes here.

### Build Tools

Spaceman uses [Gulp](http://gulpjs.com/) for its build system, alongside with [Babel](https://babeljs.io/) to compile ES6+ code and [BrowserSync](https://www.browsersync.io/) to watch files. To summarize, the `gulpfile.js` located in the project root does the following tasks:

* Compile, concatenate, minify, and lint JavaScript
* Compile, minify, autoprefix and lint Sass
* Optimize SVGs and images
* Watch files for changes, rebuild and reload browsers

#### JavaScript

Gulp will lint all `.js` files under the `assets/src/js/` path using [ESLint](https://eslint.org/) and compile all ES6+ files through [Babel](https://babeljs.io/). The compiled file will be concatenated with the files in the subdirectories `libs/`, `polyfill/` and `vendor/`, which will generate the minified, production ready `main.js` file in the `assets/dist/js/` path.

To change or update the linter configuration or ignored paths and files, use the `.eslintrc` and `.eslintignore` files located in the root directory.

#### Sass

Spaceman uses [Sass](https://sass-lang.com/) as CSS preprocessor with the SCSS syntax and the [SUIT CSS](https://github.com/suitcss/suit/blob/master/doc/naming-conventions.md) naming conventions. In the `assets/src/sass/` path you will see the following structure:

* `base/` - contains global styles, such as resets, typography and grid
* `components/` - contains each self-contained component in its own `.scss` partial
* `config/` - contains all the global variables, such as colors, breakpoints and etc.
* `layout/` - contains styling for larger layout components such as nav, header, footer, etc.
* `utils/` - contains global mixins, functions and helper selectors
* `vendor/` - contains any 3rd-party styles used in the project
* `main.scss` - output file that brings together all styles

Each subdirectory must have a `_module.scss` partial, which references all the styles in that same folder. These same partials are then referenced in the `main.scss` file:

```css
@import 'config/module';
@import 'utils/module';
@import 'base/module';
@import 'components/module';
@import 'layout/module';
@import 'vendor/module';
```

Gulp will lint all `.scss` files with [StyleLint](https://stylelint.io/) and compile Sass to CSS. Vendor prefixes will be added to the compiled file with [Autoprefixer](https://autoprefixer.github.io/) and it will be optimized using [cssnano](https://cssnano.co/), which will generate the minified, production ready `main.css` file in the `assets/dist/css/` path.

To change or update the linter configuration, use the `.stylelintrc` file located in the root directory.

#### Images and SVGs

All images and SVGs located under the directories `assets/src/img/` and `assets/src/svg/` will be optimized using [imagemin](https://github.com/sindresorhus/gulp-imagemin). The optimized files will be available in `assets/dist/img/` and `assets/dist/svg/` respectively.

#### Build and Watch
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

Sass:
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

Sass:
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

Utilities for controlling the display box type of an element.

Class | Properties
--- | ---
.block | display: block;
.inline-block | display: inline-block;
.inline | display: inline;
.table | display: table;
.table-cell | display: table-cell;
.flex | display: flex;

### Floating

Utilities for controlling the wrapping of content around an element.

Class | Properties
--- | ---
.fleft | float: left;
.fright | float: right;
.fnone | float: none;
.clear | clear: both;

### Position

Utilities for controlling how an element is positioned in the DOM.

Class | Properties
--- | ---
.relative | position: relative;
.absolute | position: absolute;
.fixed | position: fixed;

### Z-index

Utilities for controlling the stack order of an element.

Class | Properties
--- | ---
.z-index-1 | z-index: 1;
.z-index-2 | z-index: 2;
.z-index-3 | z-index: 3;
.z-index-4 | z-index: 4;
.z-index-5 | z-index: 5;
.z-index-6 | z-index: 6;

### Sizing

Utilities for controlling the width and height of an element.

Class | Properties
--- | ---
.auto-width | width: auto;
.auto-height | height: auto;
.full-width | width: 100%;
.full-height | height: 100%;
.full-size | width: 100%;<br/>height: 100%;
.auto-size | width: auto;<br/>height: auto;

### Responsive Visibility

The responsive visibility utilities allows you to hide and show elements on a specific [breakpoint](#breakpoints).

#### Hiding Elements

Use the following classes to hide an element on a specific breakpoint:

| | 480px | 600px | 840px | 960px | 1280px
--- | --- | --- | --- | --- | ---
.hide-xs | | visible | visible | visible | visible
.hide-sm | | | visible | visible | visible
.hide-md | | | | visible | visible
.hide-lg | | | | | visible
.hide-xl | | | | |

* `.hide-xs` - hides the element when the viewport width is smaller or equal to **480px**
* `.hide-sm` - hides the element when the viewport width is smaller or equal to **600px**
* `.hide-md` - hides the element when the viewport width is smaller or equal to **840px**
* `.hide-lg` - hides the element when the viewport width is smaller or equal to **960px**
* `.hide-xl` - hides the element when the viewport width is smaller or equal to **1280px**

#### Showing Elements

Use the following classes to show an element on a specific breakpoint:

| | 480px | 600px | 840px | 960px | 1280px
--- | --- | --- | --- | --- | ---
.show-xs | visible | | | |
.show-sm | visible | visible | | |
.show-md | visible | visible | visible | |
.show-lg | visible | visible | visible | visible |
.show-xl | visible | visible | visible | visible | visible

* `.show-xs` - shows the element when the viewport width is smaller or equal to **480px**
* `.show-sm` - shows the element when the viewport width is smaller or equal to **600px**
* `.show-md` - shows the element when the viewport width is smaller or equal to **840px**
* `.show-lg` - shows the element when the viewport width is smaller or equal to **960px**
* `.show-xl` - shows the element when the viewport width is smaller or equal to **1280px**

### Miscelaneos
Section content goes here.
