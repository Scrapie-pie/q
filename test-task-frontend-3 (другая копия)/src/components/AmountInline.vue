<template>
  <span class="v-amount-inline">
    ({{value}})
  </span>
</template>

<script>
//import BaseIcon from './BaseIcon.vue';
export default {
  name: "AmountInline",
  props: {
    value: {
      type: [String, Number],
      //validator() =>
      default: 'xxx'
    }
  },
}
</script>

<style lang="scss" scoped>
  .v-amount-inline {
    font-size: 12px;
    color: get-var(color, amount_inline);
  }
</style>
