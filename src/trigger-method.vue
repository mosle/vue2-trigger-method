<script lang="ts">
import Vue from "vue";

interface DataType {}

export default /*#__PURE__*/ Vue.extend({
  name: "TriggerMethod", // vue component name
  props: {
    delay: {
      type: Number,
      default: 0,
    },
  },
  data(): DataType {
    return {};
  },
  computed: {},
  methods: {},
  created(): void {
    setTimeout(() => {
      this.$emit("trigger");
    }, this.delay);
  },
});
</script>

<template></template>

<style scoped>
</style>
