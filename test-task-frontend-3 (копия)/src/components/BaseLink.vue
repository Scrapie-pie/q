<template>
  <component :is="tag" :href="href" class="link">
    <slot></slot>
    <BaseIcon v-if="icon" :icon="icon"/>
  </component>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
export default {
  name: "BaseLink",
  props: {
    tag:  { type: String, default: 'a' },
    href: { type: String, default: '#' },
    icon: String,
  },
  components: {
    BaseIcon
  }
}
</script>

<style lang="scss">
  .link {
    @include flex-it(row, 15px, true);
    align-items: center;
    color: get-var(color, blue_light);
  }
</style>
