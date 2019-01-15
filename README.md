# bulma-helpers
Library with missing **Functional / Atomic CSS classes for Bulma framework**, which doesn't require Bulma framework to work! :heart:

[![npm](https://img.shields.io/npm/v/bulma-helpers.svg)][npm-link]

<img src="https://raw.githubusercontent.com/jgthms/bulma/master/docs/images/bulma-banner.png" width="600" height="315" class="center">

- [bulma-helpers](#bulma-helpers)
  * [Quick install](#quick-install)
    + [NPM](#npm)
    + [Yarn](#yarn)
    + [Import](#import)
  * [Compatibility with Bulma](#compatibility-with-bulma)
  * [Compatibility with other CSS frameworks](#compatibility-with-other-css-frameworks)
  * [CSS only](#css-only)
  * [Browser Support](#browser-support)
  * [Customization](#customization)
    + [Customizing ranges of generated classes](#customizing-ranges-of-generated-classes)
    + [Customizing media queries](#customizing-media-queries)
    + [Customizing breakpoints](#customizing-breakpoints)
    + [Choosing modules](#choosing-modules)
  * [Documentation](#documentation)
    + [Spacing](#spacing)
      - [Margin](#margin)
        * [Margin](#margin-1)
        * [Margin for one side](#margin-for-one-side)
        * [All available sides](#all-available-sides)
        * [Default available spacing values](#default-available-spacing-values)
      - [Padding](#padding)
        * [Padding](#padding-1)
        * [Padding for one side](#padding-for-one-side)
        * [All available sides](#all-available-sides-1)
        * [Default available spacing values](#default-available-spacing-values-1)
    + [Sizing](#sizing)
        * [Width](#width)
        * [Height](#height)
        * [Default available sizing values](#default-available-sizing-values)
      - [Max / min width / height](#max---min-width---height)
        * [Max width](#max-width)
        * [Min height](#min-height)
        * [Default available sizing values](#default-available-sizing-values-1)
      - [Fraction width / height](#fraction-width---height)
        * [Full width](#full-width)
        * [Default available sizing values](#default-available-sizing-values-2)
      - [Full page width / height](#full-page-width---height)
        * [Full page width](#full-page-width)
        * [Default available sizing values](#default-available-sizing-values-3)
    + [Media queries](#media-queries)
      - [Default breakpoints](#default-breakpoints)
      - [Margin](#margin-2)
        * [Margin](#margin-3)
        * [Margin for one side](#margin-for-one-side-1)
        * [All available sides](#all-available-sides-2)
        * [Default available spacing values](#default-available-spacing-values-2)
      - [Padding](#padding-2)
        * [Padding](#padding-3)
        * [Padding for one side](#padding-for-one-side-1)
        * [All available sides](#all-available-sides-3)
        * [Default available spacing values](#default-available-spacing-values-3)
    + [Sizing](#sizing-1)
        * [Width](#width-1)
        * [Height](#height-1)
        * [Default available sizing values](#default-available-sizing-values-4)
      - [Max / min width / height](#max---min-width---height-1)
        * [Max width](#max-width-1)
        * [Min height](#min-height-1)
        * [Default available sizing values](#default-available-sizing-values-5)
      - [Fraction width / height](#fraction-width---height-1)
        * [Full width](#full-width-1)
        * [Default available sizing values](#default-available-sizing-values-6)
      - [Full page width / height](#full-page-width---height-1)
        * [Full page width](#full-page-width-1)
        * [Default available sizing values](#default-available-sizing-values-7)
    + [Flex](#flex)
        * [Row](#row)
        * [Column](#column)
        * [Align content start](#align-content-start)
        * [Justify content center](#justify-content-center)
        * [Align self baseline](#align-self-baseline)
        * [Align items flex-end](#align-items-flex-end)
        * [Nowrap](#nowrap)
    + [Border](#border)
        * [Borderless](#borderless)
        * [Border width](#border-width)
        * [Border width for one side](#border-width-for-one-side)
        * [All available sides](#all-available-sides-4)
        * [Default available sizing values](#default-available-sizing-values-8)
    + [Cursor](#cursor)
        * [Cursor's style](#cursor-s-style)
        * [All available cursors](#all-available-cursors)
    + [Misc](#misc)
        * [Blur](#blur)
        * [Blur medium](#blur-medium)
        * [Blur hard](#blur-hard)
        * [Default values for blurs](#default-values-for-blurs)
  * [Copyright and license](#copyright-and-license)

## Quick install

Installation is nearly the same as pure Bulma framework.

### NPM
```sh
npm install bulma-helpers
```
**or**

### Yarn

```sh
yarn add bulma-helpers
```
### Import
After installation, you can import the CSS file into your project using this snippet:

```sh
import 'bulma-helpers/css/bulma-helpers.min.css'
```

## Compatibility with Bulma

Bulma-helpers library complies with Bulma convention of naming classes. Most of classes are of the `is-*` and `has-*` type. Example:
```scss
.is-borderless
```
or
```scss
.has-padding-top-5
```

One exception are pure Flexbox classes, which names just reflect modifiers. Example:
```scss
.flex-row
```
or
```scss
.align-center
```

## Compatibility with other CSS frameworks

You can use Bulma-helpers with any other CSS framework or even as a standalone library, if you want to write Functional / Atomic CSS code. Keep in mind that Bulma-helpers library bases on Sass, so you will need basic knowledge of Sass to customize the library.

## CSS only

Bulma-helpers, equally to Bulma, is a **CSS** library. As such, the sole output is a single CSS file: [bulma-helpers.css](https://github.com/jmaczan/bulma-helpers/blob/master/css/bulma-helpers.css)

You can either use that file, "out of the box", or download the Sass source files to customize the variables or choose which modules do you want to use.

There is **no** JavaScript included.

## Browser Support

Bulma-helpers, equally to Bulma, uses [autoprefixer](https://github.com/postcss/autoprefixer) to make (most) Flexbox features compatible with earlier browser versions. According to [Can I use](https://caniuse.com/#feat=flexbox), Bulma is compatible with **recent** versions of:

* Chrome
* Edge
* Firefox
* Opera
* Safari

Internet Explorer (10+) is only partially supported.

## Customization

All modules are toggled on and all variables have some values by default. You can customize these values by assigning your values to variables, defined in the library. **All available variables you can find in corresponding files in `variables` directory.** Toggling off media queries (variables for this you can find in `sass/helpers/variables/media-queries.sass`, for example `$enable-flex-media-queries`) will decrease size of the library dramatically.

### Customizing ranges of generated classes

For all generated classes (such as `has-margin-bottom-*`, where `*` is value from given range) there is a simple way to change range and interval of generated classes. You can change the following variables in corresponding sass files. All variables follow the same pattern, shown below.

```scss
$sizing-range-start: 50 !default
$sizing-range-end: 400 !default
$sizing-interval: 50 !default
```

We've got `name of customized value`, such as `sizing` or `spacing`, then variable's meaning, such as `range-start`, `range-end` and `interval`.

For media queries, the rule is the same. The only difference is that rest of variable's name is preceded by `mq`.

```scss
$mq-sizing-range-start: 50 !default
$mq-sizing-range-end: 400 !default
$mq-sizing-interval: 50 !default
```

### Customizing media queries

You can decide whether you want to include media queries in your project or not. In `variables/media-queries.sass` file you can find variables which allows you to customize your Bulma-helpers. All of defined variables are built on top of the following pattern:

```scss
$enable-media-queries: true !default
```

This variables enables/disables all media queries in the project.

For choosing certain modules, such as max/min width/height sizing media queries, you can assign a value to variables such as:

```scss
$enable-sizing-max-min-width-height-media-queries: true !default
```

### Customizing breakpoints

Breakpoints are same as default breapoints in Bulma. If you want to change them, then just override the same breakpoint variables as in Bulma, for example:

```scss
$tablet: 800px
```

### Choosing modules

By default, all modules are included in result build. Even so, you can decide on your own which modules do you want to use in your project.
To achieve this, you have to remove unwanted sass modules imports from main `_all.sass` files in helpers directory or remove single file imports from `_all.sass` in corresponding modules directories.

## Documentation

All values are represented by pixels, so e.g. `has-max-width-50` class means that this element's maximal width is 50px.

### Spacing

#### Margin

##### Margin
```scss
.has-margin-5
```
gives
```scss
margin: 5px !important
```

##### Margin for one side
```scss
.has-margin-top-5
```
gives
```scss
margin-top: 5px !important
```

##### All available sides
1. top
2. right
3. bottom
4. left

##### Default available spacing values
(5, 10, 15, ..., 150)

#### Padding

In the same way as above for margin.

##### Padding
```scss
.has-padding-5
```

##### Padding for one side
```scss
.has-padding-top-5
```

##### All available sides
1. top
2. right
3. bottom
4. left

##### Default available spacing values
(5, 10, 15, ..., 150)

### Sizing

##### Width
```scss
.has-width-50
```
gives
```scss
width: 50px !important
```

##### Height
```scss
.has-height-50
```

##### Default available sizing values
(50, 100, 150, ..., 400)

#### Max / min width / height

##### Max width
```scss
.has-max-width-50
```
gives
```scss
width: 50px !important
```

##### Min height
```scss
.has-min-height-50
```
gives
```scss
min-height: 50px !important
```

##### Default available sizing values
(50, 100, 150, ..., 400)

#### Fraction width / height

##### Full width
```scss
.is-full-width
```
gives
```scss
width: 100% !important
```

```scss
.is-half-height
```
gives
```scss
height: 50% !important
```

##### Default available sizing values
full (100%), half (50%), quarter (25%)

#### Full page width / height

##### Full page width
```scss
.has-page-width
```
gives
```scss
width: 100vw !important
```

##### Default available sizing values
full (100vw/vh), half (50vw/vh), quarter (25vw/vh)

### Media queries

By default, media queries for sizing and spacing are toggled on. You can use media queries in exactly the same as in Bulma framework. Just add postfix to classname with breakpoints name, such as `-mobile` or `-widescreen-only`.

#### Default breakpoints

There are few defined breakpoints - mobile, tablet, tablet-only, touch, desktop, desktop-only, widescreen, widescreen-only, fullhd. Everything as in Bulma! You can read more [here](https://bulma.io/documentation/overview/responsiveness/).

```scss
$gap: 64px !default
$tablet: 769px !default
$desktop: 960px + (2 * $gap) !default
$widescreen: 1152px + (2 * $gap) !default
$widescreen-enabled: true !default
$fullhd: 1344px + (2 * $gap) !default
$fullhd-enabled: true !default
```

#### Margin

##### Margin
```scss
.has-margin-5-mobile
```

##### Margin for one side
```scss
.has-margin-top-5-tablet
```

##### All available sides
1. top
2. right
3. bottom
4. left

##### Default available spacing values
(5, 10, 15, ..., 150)

#### Padding

In the same way as above for margin.

##### Padding
```scss
.has-padding-5-fullhd
```

##### Padding for one side
```scss
.has-padding-top-5-widescreen
```

##### All available sides
1. top
2. right
3. bottom
4. left

##### Default available spacing values
(5, 10, 15, ..., 150)

### Flex
For all flex classes you can do all the responsive things. For example:

```scss
.flex-mobile
```

```scss
.justify-center-desktop
```

### Sizing

##### Width
```scss
.has-width-50-touch
```

##### Height
```scss
.has-height-50-mobile
```

##### Default available sizing values
(50, 100, 150, ..., 400)

#### Max / min width / height

##### Max width
```scss
.has-max-width-50-desktop
```

##### Min height
```scss
.has-min-height-50-mobile
```

##### Default available sizing values
(50, 100, 150, ..., 400)

#### Fraction width / height

##### Full width
```scss
.is-full-width-tablet
```

```scss
.is-half-height-widescreen
```

##### Default available sizing values
full (100%), half (50%), quarter (25%)

#### Full page width / height

##### Full page width
```scss
.has-page-width-mobile
```

##### Default available sizing values
full (100vw/vh), half (50vw/vh), quarter (25vw/vh)

### Flex

**Names of classes reflect modifiers**. There are modifiers for: 
1. row
2. column
3. align-content
4. justify-content
5. align-self
6. align-items
7. wrap

**Examples:**

##### Row
```scss
.flex-row
```
##### Column
```scss
.flex-column
```
##### Align content start
```scss
.align-start
```
##### Justify content center
```scss
.justify-center
```
##### Align self baseline
```scss
.align-self-baseline
```
##### Align items flex-end
```scss
.align-items-flex-end
```
##### Nowrap
```scss
.nowrap
```

### Border

##### Borderless
```scss
.is-borderless
```

##### Completely borderless
Makes cascade of borderless (applies lack of border to all tr, td and th in the table).
```scss
.is-completely-borderless
```

##### Border width
```scss
.has-border-width-3
```
gives
```scss
border-width: 3px !important
```

##### Border width for one side
```scss
.has-border-top-width-3
```
gives
```scss
border-top-width: 3px !important
```

##### All available sides
1. top
2. right
3. bottom
4. left

##### Default available sizing values
(1, 2, 3, ..., 10)

### Cursor

##### Cursor's style
```scss
.has-cursor-pointer
```
gives
```scss
cursor: pointer !important
```

##### All available cursors
1. pointer
2. grab
3. help 
4. wait 
5. crosshair 
6. not-allowed 
7. zoom-in
8. default

### Misc

##### Blur
```scss
.is-blurred
```
gives
```scss
filter: blur(15px) !important
```

##### Blur medium
```scss
.is-blurred-medium
```
gives
```scss
filter: blur(40px) !important
```

##### Blur hard
```scss
.is-blurred-hard
```
gives
```scss
filter: blur(75px) !important
```

##### Default values for blurs
(15px, 40px, 75px)

## Copyright and license

Code copyright 2018 Jędrzej Maczan. Code released under the MIT license. README bases on Bulma README file.

[npm-link]: https://www.npmjs.com/package/bulma-helpers
