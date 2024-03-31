# leta-vue

This template should help get you started developing with Vue 3 in Vite.

## Recommended IDE Setup

[VSCode](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur).

## Type Support for `.vue` Imports in TS

TypeScript cannot handle type information for `.vue` imports by default, so we replace the `tsc` CLI with `vue-tsc` for type checking. In editors, we need [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) to make the TypeScript language service aware of `.vue` types.

## Customize configuration

See [Vite Configuration Reference](https://vitejs.dev/config/).

## Project Setup

```sh
npm install
```

### Compile and Hot-Reload for Development

```sh
npm run dev
```

### Type-Check, Compile and Minify for Production

```sh
npm run build
```

### Lint with [ESLint](https://eslint.org/)

```sh
npm run lint
```



# Code style

## Naming conventions

### 'The' prefix for components that are used only once

If a component is used only once, it should be prefixed with 'The'. This is to indicate that the component is unique and is not meant to be reused.

Examples:
- TheHeader.vue
- TheFooter.vue
- TheButton.vue

### 'Base' prefix for components that are meant to be reused

If a component is meant to be reused, it should be prefixed with 'Base'. This is to indicate that the component is a base component that can be used in multiple places.

Examples:
- BaseButton.vue
- BaseInput.vue
- BaseCard.vue

