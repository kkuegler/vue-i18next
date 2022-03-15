# Getting started

Install the package via

<code-group>
<code-block title="npm">
```bash
npm install @dotbase/vue-i18next
``` 
</code-block>

<code-block title="yarn">
```bash
yarn add @dotbase/vue-i18next
```
</code-block>

<code-block title="pnpm">
```bash
pnpm add @dotbase/vue-i18next
```
</code-block>
</code-group>

## Requirements

- Vue.js `2.x`
    - there is a separate [Vue 3 version](https://github.com/kkuegler/vue-i18next/tree/vue-3) of this library
- i18next `19.x` or newer

## Setup

See the [i18next docs](https://www.i18next.com/overview/api#init) for setting it up. Vue-i18next does not need a lot of setup on top of that.

```javascript
import Vue from 'vue';
import i18next from 'i18next';
import VueI18Next from '@dotbase/vue-i18next';

i18next.init({
  lng: 'de',
  resources: {
    ...
  }
});

Vue.use(VueI18Next, {i18next});

new Vue({
  ...
});
```

## Simple usage
Use the instance function `$t` in your Vue components to translate. See [Component based localization](./component.md) for more details.
The [i18next documentation](https://www.i18next.com/) details all the translation options available through `$t()` (also known as [`t()` in the i18next docs](https://www.i18next.com/overview/api#t)).

```vue
<template>
    <div class="container">
     {{$t("greeter.hello-world" }}
    </div>
<template>

<script>
export default({
  // ...
  methods: {
    logSomething() {
      console.log(this.$t("common.hello"))
    }
  }
});
</script>
```

## Plugin options

You can use these options during plugin registration: 

```js
Vue.use(VueI18Next, {
  i18next: myI18next,
  rerenderOn: ['initialized', 'languageChanged', 'loaded'],
});
```

| Name | | Description |
| --- | --- | --- |
| **i18next** | Required | The 'i18next' instance to use. |
| **rerenderOn** | Optional<hr>Default: Refresh on all relevant events. | Listen for 'i18next' events and refreshes components that use translations.<br>This is a string array. Supported values includ: `'initialized'`, `'languageChanged'`, `'loaded'`, `'added'` and `'removed'`.<br>Check the [i18next events documentation](https://www.i18next.com/overview/api#events) for more information. For `'added'` and `'removed'` see the [i18next store documentation](https://www.i18next.com/overview/api#store-events) |

