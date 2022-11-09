<template>
  <div class="v-Categories-slider">
    <BaseContainer class="wrapper">
      <VSlick :options="slickOptions">
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
        <VCategory></VCategory>
      </VSlick>
      <div class="fill"></div>
    </BaseContainer>
  </div>
</template>

<script>
import 'slick-carousel/slick/slick.css';
import VSlick from 'vue-slick';
import BaseIcon from './BaseIcon.vue';
import BaseField from './BaseField.vue';
import BaseButton from './BaseButton.vue';
import BaseContainer from './BaseContainer.vue';
import VCategory from './VCategory.vue';
export default {
  name: 'CategoriesSlider',
  data() {
    return {
      slickOptions: {
        slidesToShow: 5,
        prevArrow: null,
        nextArrow: null,
        autoplay: true,
      },
    };
  },
  components: {
    BaseIcon,
    BaseField,
    BaseButton,
    BaseContainer,
    VSlick,
    VCategory
  }
}
</script>

<style lang="scss" scoped>
.v-Categories-slider {
  margin-bottom: 40px;
  .wrapper {
    position: relative;
  }
  .fill {
    right: 0;
    top: 0;
    bottom: 0;
    position: absolute;
    height: 100%;
    width: 150px;
    background: linear-gradient(269.76deg, #FFFFFF 62.83%, rgba(255, 255, 255, 0) 145.7%);
  }
}

</style>
