# lavu-grid

A Polymer 1.x Responsive Grid based on Material Design [Grid lists](http://www.google.com/design/spec/components/grid-lists.html)

The CSS from [Material Design Lite grid](https://github.com/google/material-design-lite/tree/master/src/grid) is used as a base, so most of this documentaion is copy pasted from that URL.

## Introduction
The `lavu-grid` **grid** component is a simplified method for laying out content for multiple screen sizes. It reduces the usual coding burden required to correctly display blocks of content in a variety of display conditions.

The `lavu-grid` grid is defined and enclosed by a container element. A grid has 14 columns in the large (desktop) screen size, 12 in the medium (desktop) size, 8 in the small (tablet size), and 4 in the extra small (phone) size, each size having predefined margins and gutters. Cells are laid out sequentially in a row, in the order they are defined, with some exceptions:

- If a cell doesn't fit in the row in one of the screen sizes, it flows into the following line.
- If a cell has a specified column size equal to or larger than the number of columns for the current screen size, it takes up the entirety of its row.

You can set a maximum grid width, after which the grid stays centered with padding on either side, by setting its `max-width` CSS property.





## Dependencies

Element dependencies are managed via [Bower](http://bower.io/). You can
install that via:

    npm install -g bower

Then, go ahead and download the element's dependencies:

    bower install


## Playing With Your Element

If you wish to work on your element in isolation, we recommend that you use
[Polyserve](https://github.com/PolymerLabs/polyserve) to keep your element's
bower dependencies in line. You can install it via:

    npm install -g polyserve

And you can run it via:

    polyserve

Once running, you can preview your element at
`http://localhost:8080/components/lavu-grid/`, where `lavu-grid` is the name of the directory containing it.


## Testing Your Element

Simply navigate to the `/test` directory of your element to run its tests. If
you are using Polyserve: `http://localhost:8080/components/lavu-grid/test/`

### web-component-tester

The tests are compatible with [web-component-tester](https://github.com/Polymer/web-component-tester).
Install it via:

    npm install -g web-component-tester

Then, you can run your tests on _all_ of your local browsers via:

    wct

#### WCT Tips

`wct -l chrome` will only run tests in chrome.

`wct -p` will keep the browsers alive after test runs (refresh to re-run).

`wct test/some-file.html` will test only the files you specify.


## License

Licensed under the **[Apache License, Version 2.0](http://www.apache.org/licenses/LICENSE-2.0)** (the "License");
you may not use this software except in compliance with the License.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
