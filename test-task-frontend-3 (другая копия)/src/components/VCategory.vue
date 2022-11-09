<template>
  <div class="category">
    <img src="@/assets/img/Rectangle.jpg" class="image">
    <div class="content">
      <div class="title">Название категории</div>
      <div class="amount">134 товара</div>
    </div>
  </div>
</template>

<script>
import VSlick from 'vue-slick';
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';
import BaseButton from './BaseButton.vue';
import BaseContainer from './BaseContainer.vue';
export default {
  name: 'VCategory',
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

<style lang="scss" scoped>
.category {
  display: flex !important;
  align-items: center;
  gap: 10px;
  .image {
    @include create-figure(60px, $color: #C4C4C4, $radius: 3px);
  }
  .content {
    display: flex !important;
    flex-direction: column;
    // align-items: center;
    gap: 10px;
  }
  .title {
    font-size: 14px;
  }
  .amount {
    font-size: 12px;
  }
}

</style>
