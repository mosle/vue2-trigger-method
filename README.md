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

```html
<div id="app">
  <div v-if="show">this will be shown after 2000 ms</div>

  <trigger-method @trigger="triggered"></trigger-method>
  <trigger-method @trigger="triggeredAfter(1000)" :delay="1000"></trigger-method>
  <trigger-method @trigger="show = true" :delay="2000"></trigger-method>
</div>
```

```js
const vue = new Vue(
    el:"#app",
    data(){
        return {
            show:false
        }
    },
    methods:{
        triggered() {
            console.log("triggered");
        },
        triggeredAfter(ms) {
            console.log(`called after ${ms}ms.`);
        }
    }
);
```

### On Component

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
