<template>
  <form class="header-search">
    <BaseField v-model="value" type="text" placeholder="Поиск" icon="search">
      <template #right>
        <BaseIcon icon="search-settings"></BaseIcon>
      </template>
    </BaseField>
  </form>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';

export default {
  name: 'HeaderSearch',
  data() {
    return {
      value: ''
    }
  },
  components: {
    BaseIcon,
    BaseField,
  }
}
</script>

<style lang="scss">
.header-search {

}
</style>
