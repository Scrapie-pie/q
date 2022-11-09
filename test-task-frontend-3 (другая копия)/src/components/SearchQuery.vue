<template>
  <form class="search-query" @submit.prevent="submit">
    <BaseContainer>
      <div class="wrapper">
        <BaseField v-model="value" type="text" placeholder="Поиск" icon="search-query" resizable>
          <template #inlineAfter>
            <BaseIcon icon="cross"></BaseIcon>
          </template>
          <template #right>
            <BaseButton mod="primary">Найти</BaseButton>
          </template>
        </BaseField>
        <BaseButton mod="secondary">Закрыть</BaseButton>
      </div>

      <!-- <BaseInputz @input="val=>value=val"></BaseInputz> -->
    </BaseContainer>
  </form>
</template>

<script>
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';
import BaseButton from './BaseButton.vue';
import BaseContainer from './BaseContainer.vue';
import BaseInputz from './BaseInputz.vue';
export default {
  name: 'SearchQuery',
  data() {
    return {
      value: ''
    }
  },
  methods: {
    submit() {
      console.log(this.value)
    }
  },
  components: {
    BaseIcon,
    BaseField,
    BaseButton,
    BaseContainer,
    BaseInputz
  }
}
</script>

<style lang="scss" scoped>
.search-query {
  margin-bottom: 30px;

  .wrapper {
    @include flex-it(row, 10px);
  }

  .test {

  }
}
</style>
