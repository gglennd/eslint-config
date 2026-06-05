# @gglennd/eslint-config

Shareable ESLint configuration based on [@antfu/eslint-config](https://github.com/antfu/eslint-config) with sensible defaults.

## Features

- TypeScript support enabled by default
- Code formatters configured
- Stylistic rules: 2-space indent, semicolons, double quotes
- Import sorting with `perfectionist`
- Kebab-case filename convention
- `type` preferred over `interface` for TypeScript

## Installation

```bash
npm install -D @gglennd/eslint-config eslint-plugin-format
# or
pnpm add -D @gglennd/eslint-config eslint-plugin-format
# or
yarn add -D @gglennd/eslint-config eslint-plugin-format
```

### React (Optional)

If using React, install the required plugins:

```bash
npm install -D @eslint-react/eslint-plugin eslint-plugin-react-refresh
# or
pnpm add -D @eslint-react/eslint-plugin eslint-plugin-react-refresh
```

## Usage

Create an `eslint.config.mjs` file:

```js
import defineConfig from "@gglennd/eslint-config";

export default defineConfig();
```

### Customization

You can pass options to override defaults:

```js
import defineConfig from "@gglennd/eslint-config";

export default defineConfig({
  // Override default options
  stylistic: {
    indent: 4,
    semi: false,
  },
}, {
  // Add additional ESLint rules
  rules: {
    "no-unused-vars": "warn",
  },
});
```

### React

```js
import defineConfig from "@gglennd/eslint-config";
import react from "@eslint-react/eslint-plugin";
import reactRefresh from "eslint-plugin-react-refresh";

export default defineConfig(
  {
    react: true,
  },
  {
    rules: {
    "react-refresh/only-export-components": ["off"],
    "react/no-context-provider": ["off"],
    "react/no-use-context": ["off"],
    },
  },
);
```

## License

MIT
