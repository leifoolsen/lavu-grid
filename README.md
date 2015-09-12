# lavu-grid

<img src="lavu-grid.jpg" width="100%; max-width: 1200px; margin: 0 auto;" />

The `lavu-grid` is a Polymer 1.x Responsive Grid and defines a container for html elements with `role="cell"` or `lavu-cell` custom elements.

CSS from [Material Design Lite grid](https://github.com/google/material-design-lite/tree/master/src/grid) is used as a base, so a large part of the documentation is copy pasted from the [Material Design Lite](http://www.getmdl.io/index.html) layout [GRID](http://www.getmdl.io/components/index.html#layout-section/grid) section.

## Introduction

The `lavu-grid` **grid** component is a simplified method for laying out content for multiple screen sizes. It reduces the usual coding burden required to correctly display blocks of content in a variety of display conditions.

A grid has 16 columns in the large (desktop) screen size, 12 in the medium (desktop) size, 8 in the small (tablet size), and 4 in the extra small (phone) size, each size having predefined margins and gutters set via custom css properties. Cells are laid out sequentially in a row, in the order they are defined, with some exceptions:

- If a cell doesn't fit in the row in one of the screen sizes, it flows into the following line.
- If a cell has a specified column size equal to or larger than the number of columns for the current screen size, it takes up the entirety of its row.

Style the `lavu-grid` as desired (colors, font size, maximum width, etc.), by setting CSS properties in `--lavu-grid` mixin. By setting a `max-width` CSS property in `--lavu-grid` mixin, the grid stays centered with padding on either side.


## Demo and Documentaion

[See the component page](http://leifoolsen.github.io/lavu-grid/).


## Install
Install the component using [Bower](http://bower.io/):

```sh
$ bower install leifoolsen/lavu-grid --save
```


## Usage

#### Import Custom Element:

```html
<link rel="import" href="../bower_components/lavu-grid/lavu-grid.html">
```

#### Start using it:

```html
<lavu-grid>
  <div role="cell">4</div>
  <div role="cell">4</div>
  <div role="cell">4</div>
  <div role="cell">4</div>
</lavu-grid>
```

This example renders a grid with four cells. Each cell spans four columns.

#### Listen to media query changes (optional):

```html
<lavu-grid on-media-query-changed='_mediaQueryChanged'>
  ...
</lavu-grid>

<script>
  ...
  _mediaQueryChanged: function(e) {
    if(this.$$('lavu-grid:first-child') == e.target) {
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
  }' >
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

## License

Licensed under the **[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)** (the "License");
you may not use this software except in compliance with the License.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

##### TODO
- Add reordering
- Add offset
