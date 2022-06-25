# uinix-theme-spec-theme-ui

[![Build][build-badge]][build]
[![Coverage][coverage-badge]][coverage]
[![Downloads][downloads-badge]][downloads]
[![Size][bundle-size-badge]][bundle-size]

The [`theme-ui`][theme-ui] theme spec usable by [`uinix-theme`][uinix-theme].

Visit the [Theme Playground] for interactive demos.

## Contents

- [Install](#install)
- [Use](#use)
- [API](#api)
- [Related](#related)
- [License](#license)

## Install

This package is [ESM-only] and requires Node 12+.

```sh
npm install uinix-theme-spec-theme-ui
```

## Use

`uinix-theme-spec-theme-ui` can be used officially with [`uinix-theme`][uinix-theme] or [`uinix-ui`][uinix-ui].

```js
import {createTheme} from 'uinix-theme';
import themeSpec from 'uinix-theme-spec-theme-ui';

const theme = createTheme({
  colors: {
    brand: {
      primary: 'red',
      link: 'blue',
    },
  },
  space: {
    s: 4,
    m: 8,
    l: 16,
  },
  unsupportedThemeProperty: {}
}, themeSpec);


console.log(theme);
```

Yields the following theme object.

```js
const theme = {
  borders: {},
  borderStyles: {},
  borderWidths: {},
  colors: {
    brand: {
      primary: 'red',
      link: 'blue',
    },
  },
  fonts: {},
  fontSizes: {},
  fontWeights: {},
  letterSpacings: {},
  lineHeights: {},
  opacities: {},
  radii: {},
  shadows: {},
  sizes: {},
  space: {
    s: 4,
    m: 8,
    l: 16,
  },
  transforms: {},
  zIndices: {},
};
```

Apply the `theme` and `themeSpec` to a theme renderer.

```js
import {createThemeRenderer} from 'uinix-theme';

const renderer = createThemeRenderer({
  theme,
  themeSpec,
});
```

Initialize the renderer and render a themed style.

```js
const style = {
  color: 'brand.primary',
  padding: 'm',
  ':hover > a': {
    color: 'brand.link',
    padding: 's',
  },
};

renderer.renderStyle(style);
```

Yields the following rendered CSS

```css
.x {
  color: red;
  padding: 8px;
}
.x:hover > a {
  color: blue;
  padding: 4px
}
```

See [`uinix-theme`][uinix-theme] and [`theme-ui`][theme-ui] for more details.

## API

`uinix-theme-spec-theme-ui` only has a single default export.

### `spec (ThemeSpec)`

A [`theme-ui`][theme-ui] theme spec, usable by a theme renderer.

### Related

- [`uinix-theme`][uinix-theme]
- [`uinix-theme-spec`][uinix-theme-spec]
- [`uinix-ui`][uinix-ui]
- [`theme-ui`][theme-ui]

### License

[MIT][license] © [Chris Zhou][author]

<!-- project -->

[author]: https://github.com/chrisrzhou
[license]: https://github.com/uinix-js/uinix-theme-spec-theme-ui/blob/main/license
[build]: https://github.com/uinix-js/uinix-theme-spec-theme-ui/actions
[build-badge]: https://github.com/uinix-js/uinix-theme-spec-theme-ui/workflows/main/badge.svg
[coverage]: https://codecov.io/github/uinix-js/uinix-theme-spec-theme-ui
[coverage-badge]: https://img.shields.io/codecov/c/github/uinix-js/uinix-theme-spec-theme-ui.svg
[downloads]: https://www.npmjs.com/package/uinix-theme-spec-theme-ui
[downloads-badge]: https://img.shields.io/npm/dm/uinix-theme-spec-theme-ui.svg
[bundle-size]: https://bundlephobia.com/result?p=uinix-theme-spec-theme-ui
[bundle-size-badge]: https://img.shields.io/bundlephobia/minzip/uinix-theme-spec-theme-ui.svg
[uinix-js]: https://github.com/uinix-js/
[uinix philosophy]: https://github.com/uinix-js#the-uinix-philosophy
[uinix-ui]: https://github.com/uinix-js/uinix-ui

<!-- defs -->
[ESM-only]: https://gist.github.com/sindresorhus/a39789f98801d908bbc7ff3ecc99d99c
[theme playground]: https://uinix.dev/tools/uinix-theme-playground
[theme-ui]: https://github.com/system-ui/theme-ui
[uinix-theme]: https://github.com/uinix-js/uinix-theme
[uinix-theme-spec]: https://github.com/uinix-js/uinix-theme-spec
[uinix-ui]: https://github.com/uinix-js/uinix-ui
