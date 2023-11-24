# Vant Auto Import Resolver

English | [简体中文](./README.zh-CN.md)

`@vant/auto-import-resolver` is a resolver for [unplugin-vue-components](https://github.com/unplugin/unplugin-vue-components) that enables on-demand importing of Vant components.

### Features

- Supports `Vite`, `Webpack`, `Rspack`, `Vue CLI`, `Rollup`, `esbuild`, and more.
- Automatically imports the corresponding CSS styles for the components.
- Supports SSR (Server-Side Rendering).

### Installation

```shell
# via npm
npm i @vant/auto-import-resolver unplugin-vue-components -D

# via yarn
yarn add @vant/auto-import-resolver unplugin-vue-components -D

# via pnpm
pnpm add @vant/auto-import-resolver unplugin-vue-components -D

# via Bun
bun add @vant/auto-import-resolver unplugin-vue-components -D
```

## Usage

### Vite

```ts
// vite.config.ts
import Components from 'unplugin-vue-components/vite';
import { VantResolver } from '@vant/auto-import-resolver';

export default defineConfig({
  plugins: [
    Components({
      resolvers: [VantResolver()],
    }),
  ],
});
```

### Rollup

```ts
// rollup.config.js
import Components from 'unplugin-vue-components/rollup';
import { VantResolver } from '@vant/auto-import-resolver';

export default {
  plugins: [
    Components({
      resolvers: [VantResolver()],
    }),
  ],
};
```

### Webpack

```ts
// webpack.config.js
import Components from 'unplugin-vue-components/webpack';
import { VantResolver } from '@vant/auto-import-resolver';

module.exports = {
  plugins: [
    Components({
      resolvers: [VantResolver()],
    }),
  ],
};
```

### Rspack

```ts
// rspack.config.js
import Components from 'unplugin-vue-components/rspack';
import { VantResolver } from '@vant/auto-import-resolver';

module.exports = {
  plugins: [
    Components({
      resolvers: [VantResolver()],
    }),
  ],
};
```

### Vue CLI

```ts
// vue.config.js
import Components from 'unplugin-vue-components/webpack';
import { VantResolver } from '@vant/auto-import-resolver';

module.exports = {
  configureWebpack: {
    plugins: [
      Components({
        resolvers: [VantResolver()],
      }),
    ],
  },
};
```

### esbuild

```ts
// esbuild.config.js
import { build } from 'esbuild';
import Components from 'unplugin-vue-components/esbuild';
import { VantResolver } from '@vant/auto-import-resolver';

build({
  plugins: [
    Components({
      resolvers: [VantResolver()],
    }),
  ],
});
```

## Options

### importStyle

Whether to automatically import the corresponding styles of the components.

- **Type:** `boolean`
- **Default:** `true`
- **Example:**

```ts
Components({
  resolvers: [
    VantResolver({
      // Disable style import
      importStyle: false,
    }),
  ],
});
```

### module

Specifies the type of module to be imported.

- **Type:** `'esm' | 'cjs'`
- **Default:** `'esm'`
- **Example:**

```ts
Components({
  resolvers: [
    VantResolver({
      module: 'cjs',
    }),
  ],
});
```

### ssr

- **Type:** `boolean`
- **Default:** `undefined`

This option is deprecated. Please use the `module` option to set the module type.