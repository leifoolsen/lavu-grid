# lavu-grid

The `lavu-grid` is a Polymer 1.x Responsive Grid and defines a container for the `lavu-grid-cell` components.

CSS from [Material Design Lite grid](https://github.com/google/material-design-lite/tree/master/src/grid) is used as a base, so a large part of the documentation is copy pasted from the [Material Design Lite](http://www.getmdl.io/index.html) layout [GRID](http://www.getmdl.io/components/index.html#layout-section/grid) section.

## Introduction

The `lavu-grid` **grid** component is a simplified method for laying out content for multiple screen sizes. It reduces the usual coding burden required to correctly display blocks of content in a variety of display conditions.

A grid has 16 columns in the large (desktop) screen size, 12 in the medium (desktop) size, 8 in the small (tablet size), and 4 in the extra small (phone) size, each size having predefined margins and gutters set via custom css properties. Cells are laid out sequentially in a row, in the order they are defined, with some exceptions:

- If a cell doesn't fit in the row in one of the screen sizes, it flows into the following line.
- If a cell has a specified column size equal to or larger than the number of columns for the current screen size, it takes up the entirety of its row.

You can set a maximum grid width, after which the grid stays centered with padding on either side, by setting a `max-width` CSS property in `--lavu-grid` mixin.


## Demo and Documentaion

See the component page.


## Install
Install the component using [Bower](http://bower.io/):

```sh
$ bower install leifoolsen/lavu-grid --save
```


## Usage

#### Import Custom Element:

```html
<link rel="import" href="bower_components/lavu-grid/lavu-grid.html">
```

#### Start using it:

```html
<lavu-grid>
  <lavu-grid-cell>4</lavu-grid-cell>
  <lavu-grid-cell>4</lavu-grid-cell>
  <lavu-grid-cell>4</lavu-grid-cell>
  <lavu-grid-cell>4</lavu-grid-cell>
</lavu-grid>
```

This example renders a grid with four cells. Each cell spans four columns.

#### Listen to media query changes (optional):

```html
<mdl-grid on-media-query-changed='_mediaQueryChanged'>
  ...
</mdl-grid>

<script>
  ...
  _mediaQueryChanged: function(e) {
    if(this.$$('mdl-grid:first-child') == e.target) {
      console.log('media-query-changed: ' 
        + e.detail.screenClass + ', ' + e.detail.mediaQuery);
    }
  }
</script>

```

#### Change default media query values (optional)

```html
<lavu-grid media-queries='
  { "queryXs": "(max-width: 768px)",
    "querySm": "(min-width: 769px) and (max-width: 991px)",
    "queryMd": "(min-width: 992px) and (max-width: 1199px)",
    "queryLg": "(min-width: 1200px)"
  }'>
  ...
</lavu-grid>
```


## Running locally

### polyserve

```
$ npm install --global polyserve
```

```
$ polyserve
```

## Reference 

### Styling

The following custom properties and mixins are available for styling:

Custom property               | Description | Default
------------------------------|-------------|----------
`--grid-xs-columns`           | Columns extra small devices (phones) | 4
`--grid-xs-gutter`            | Gutter extra small devices (phones)  | `--grid-lg-gutter`
`--grid-xs-margin`            | Margin extra small devices (phones)  | `--grid-lg-margin`
`--grid-sm-columns`           | Columns small devices (tablets)      | 8;
`--grid-sm-gutter`            | Gutter small devices (tablets)       | `--grid-lg-gutter`
`--grid-sm-margin`            | Margin small devices (tablets)       | `--grid-lg-margin`
`--grid-md-columns`           | Columns medium devices (desktops)    | 12;
`--grid-md-gutter`            | Gutter medium devices (desktops)     | `--grid-lg-gutter`
`--grid-md-margin`            | Margin medium devices (desktops)     | `--grid-lg-gutter`
`--grid-lg-columns`           | Columns large devices (desktops)     | 16;
`--grid-lg-gutter`            | Gutter large devices (desktops)      | 4px;
`--grid-lg-margin`            | Margin large devices (desktops)      | 4px;
`--grid-cell-default-columns` | Default number of columns            | `--grid-xs-columns`
`--lavu-grid`                 | Mixin applied to the grid            | `{}`


## License

Licensed under the **[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)** (the "License");
you may not use this software except in compliance with the License.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
