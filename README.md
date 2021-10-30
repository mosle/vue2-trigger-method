## Installation

```sh
npm install --save vue2-trigger-method
```

```sh
yarn add vue2-trigger-method
```

## Usage

### Global registration

```js
import TriggerMethod from "vue2-trigger-method";
Vue.use(TriggerMethod);
```

### Local registration

```js
import TriggerMethod from "vue2-trigger-method";

export default {
  components: {
    TriggerMethod,
  },
};
```

### Usage

```vue
<template>
  <trigger-method @trigger="triggered"></trigger-method>
  <trigger-method @trigger="triggeredAfter(1000)" :delay="1000"></trigger-method>
</template>
<script>
import { Component, Vue } from "vue-property-decorator";

@Component({})
export default class DemoClass extends Vue {
  triggered() {
    console.log("triggered");
  }
  triggeredAfter(ms) {
    console.log(`called after ${ms}ms.`);
  }
}
</script>
```
