<template>
  <div class="breadcrumbs">
    <BaseContainer>
      <div class="breadcrumbs-content">
        <span class="breadcrumbs-item">Главная</span>
        <span class="breadcrumbs-item">Контакты</span>
      </div>
    </BaseContainer>
  </div>
</template>

<script>
import BaseContainer from './BaseContainer.vue';

export default {
    name: "TheBreadcrumbs",
    components: { BaseContainer }
}
</script>

<style lang="scss">
.breadcrumbs {
  margin-bottom: 60px;

  &-item {
    @include h(6, get-var(color, graphit));

    &:not(:last-child):after {
      content: '\00a0-\00a0';
    }

    &:last-child {
      font-weight: 600;
    }
  }
}
</style>
