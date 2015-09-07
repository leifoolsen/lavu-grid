# &lt;lavu-grid&gt;

A Polymer 1.x Responsive Grid.

The CSS from [Material Design Lite grid](https://github.com/google/material-design-lite/tree/master/src/grid) is used as a base, so most of this documentaion is copy pasted from that URL.


## Introduction

The `lavu-grid` **grid** component is a simplified method for laying out content for multiple screen sizes. It reduces the usual coding burden required to correctly display blocks of content in a variety of display conditions.

A grid has 16 columns in the large (desktop) screen size, 12 in the medium (desktop) size, 8 in the small (tablet size), and 4 in the extra small (phone) size, each size having predefined margins and gutters. Cells are laid out sequentially in a row, in the order they are defined, with some exceptions:

- If a cell doesn't fit in the row in one of the screen sizes, it flows into the following line.
- If a cell has a specified column size equal to or larger than the number of columns for the current screen size, it takes up the entirety of its row.

You can set a maximum grid width, after which the grid stays centered with padding on either side, by setting its `max-width` CSS property in `--lavu-grid` cusom property.


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
  <lavu-grid-cell span="4" span-md="4" span-sm="3" span-xs="3">4, md4, sm3, xs3</lavu-grid-cell>
  <lavu-grid-cell span="6" span-md="3" span-sm="3" span-xs="1">6, md3, sm3, xs1</lavu-grid-cell>
  <lavu-grid-cell span="6" span-md="5" span-sm="2" hide-xs>6, md5, sm2, hide-xs</lavu-grid-cell>
</lavu-grid>
```

#### Listen to media query changes (optional):

```html
<mdl-grid on-media-query-changed='_mediaQueryChanged'>
  ...
</mdl-grid>

<script>
  ...
  _mediaQueryChanged: function(e) {
    if(this.$$('mdl-grid:first-child') == e.target) {
      console.log('media-query-changed: ' + e.detail.screenClass + ', ' + e.detail.mediaQuery);
    }
  }
</script>

```

## Styling

The following custom properties and mixins are available for styling:

Custom property | Description | Default
----------------|-------------|----------
`--lavu-grid`   | Mixin applied to the grid | `{}`


## API Reference


## Events


## License

Licensed under the **[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)** (the "License");
you may not use this software except in compliance with the License.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
