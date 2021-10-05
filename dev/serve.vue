<script lang="ts">
import Vue from "vue";
import TriggerMethod from "@/trigger-method.vue";

export default Vue.extend({
  name: "ServeDev",
  data() {
    return {
      a: "scope test A",
      b: "scope test B",
    };
  },
  components: {
    TriggerMethod,
  },
  methods: {
    test1() {
      console.log(`test 1 called (${this.a})`);
    },
    test2() {
      console.log(`test 2 called (${this.b})`);
    },
    test3(arg: string) {
      console.log(`test 3 called ${arg}`);
    },
  },
});
</script>

<template>
  <div id="app">
    <trigger-method @trigger="test1" />
    <trigger-method :delay="1000" @trigger="test2" />
    <trigger-method :delay="2000" @trigger="test3('pass argument')" />
  </div>
</template>
