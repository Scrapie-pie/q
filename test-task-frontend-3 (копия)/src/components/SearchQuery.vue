<template>
  <form class="search-query">
    <BaseContainer>
      <BaseField v-model="value" type="text" placeholder="Поиск" icon="search-query">
        <template #right>
          Поиск
        </template>
      </BaseField>
    </BaseContainer>
  </form>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';
import BaseButton from './BaseButton.vue';
import BaseContainer from './BaseContainer.vue';
export default {
  name: 'SearchQuery',
  data() {
    return {
      value: ''
    }
  },
  components: {
    BaseIcon,
    BaseField,
    BaseButton,
    BaseContainer
  }
}
</script>

<style lang="scss">
.search-query {

}
</style>
