# Installation

## Direct Download / CDN

<https://unpkg.com/@dotbase/vue-i18next/dist/index.js>

[unpkg.com](https://unpkg.com) provides NPM-based CDN links. The above link will always point to the latest release on NPM. You can also use a specific version/tag via URLs like <https://unpkg.com/@dotbase/vue-i18next@1.0.3/dist/index.js>

    
```html    
<script src="https://unpkg.com/vue@2/dist/vue.js"></script>
<script src="https://unpkg.com/i18next@21/i18next.js"></script>
<script src="https://unpkg.com/@dotbase/vue-i18next@1/dist/index.js"></script>
```

You need to explicitly install the `vue-i18next` plugin via `Vue.use(VueI18Next, { i18next });`

## Using a package manager
If you use some bundler like Webpack, Vite, etc. you can install vue-i18next like this:

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
    

You need to explicitly install the `vue-i18next` plugin via `Vue.use()`:
    
```javascript
import Vue from 'vue';
import i18next from 'i18next';
import VueI18Next from '@dotbase/vue-i18next';

i18next.init({/*...*/});
Vue.use(VueI18Next, { i18next });
```

## Dev Build

You can clone directly from GitHub and build `@dotbase/vue-i18next` yourself if you want to use the latest dev build.

```sh
git clone https://github.com/dot-base/vue-i18next.git node_modules/@dotbase/vue-i18next
cd node_modules/@dotbase/vue-i18next
npm i
npm run build
```
