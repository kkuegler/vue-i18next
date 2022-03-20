# SSR

When using Server Side Rendering (SSR), vue-i18next makes sure to not introduce memore leaks. To do that, two vue-i18next features are not available on the server.

## No component-specific messages
Neither [`<i18>` blocks](./single-file-component.md) nor translations defined via [`i18nOptions.messages`](./i18n-options.html#messages) are supported. These are usually registered by vue-i18next with i18next
in a Vue lifecycle hook and de-registered when the component is dismounted.

As there is [no `unmounted()` life-cycle hook](https://vuejs.org/guide/scaling-up/ssr.html#component-lifecycle-hooks) during SSR, we ignore these messages.


## No `rerenderOn` updates
The `rerenderOn` plugin option is ignored on the server. The i18next instance needs to be properly set up with e.g. language and messages
before rendering. Because of this, there is no need for such i18next reactivity.